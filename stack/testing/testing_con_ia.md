# testing con ia
## El Cambio
Ya no es tan importante saber programar el test (eso lo hace la IA en segundos), importa saber qué probar (reglas de negocio bien definidas).

## El Catálogo de Fallas
Es tu lista de control de errores posibles. Se utiliza para cada uno de los repos en este caso se utiliza para `amounts.py` Sirve para dos cosas:
- Prompt: Le dices a la IA "haz un test para esta falla del catálogo".
- Rúbrica: Revisas si la IA hizo el test completo o solo tomo el camino fácil.
### Las 5 Familias de Fallas
- Frontera: Probar los límites (0, mínimo, máximo).
- Equivalencia: Positivo, negativo, no numérico.
- Null/Vacío: Datos faltantes (None, texto vacío).
- Carrera: Peticiones dobles/simultáneas.
- Seguridad: Hacer lo que no debes (autorización).
### Confirmado vs. Pendiente
- Confirmado (Técnico): Lanzó un error feo (AttributeError) en vez de uno controlado. Se arregla ya.
- Pendiente (Negocio): ¿El monto 0 cobra comisión mínima? La IA no decide la regla, le toca al humano definirla.

vas a utilizar el prompt 01



## Prompt de Tres capas para test
Estructura básica: Tres capas para definir qué hace, dónde se rompe y cómo se estructura el test para auditarlo fácil.

### Sistema bajo prueba (¿Qué hace?)
- Describes firmas, contratos y dependencias.
- Objetivo: Dar contexto técnico duro para evitar que la IA alucine comportamientos inexistentes.
### Modos de falla (¿Dónde se rompe?)
- Pegas las clases de equivalencia y casos límite del Catálogo de Fallas.
- Objetivo: Inyectar el criterio del negocio esto lo debes realizar tu y forzar a la IA a salir del happy path.
### Forma del test (¿Cómo se prueba?)
- Exiges un test por clase, fixtures realistas y patrón AAA (Arrange-Act-Assert).
- Alerta: Evita datos estáticos/perezosos de la IA que no presionen el código (ej. probar montos con decimales/céntimos reales en vez de enteros simples).

Te vas a guiar del prompt 2 y 3
## Mutation testing
La trampa: Si los tests están en verde no significa que el código esté bien; la IA genera fácil tests decorativos (pasan sin presionar el código).
- Concepto: Consiste en inyectar fallas conocidas (mutantes) en el código para medir si tu suite de pruebas realmente las detecta.
- Proceso (ej. refunds.py):
    - La herramienta altera el código original (ej. cambia un > por >=).
    - Ejecutas los tests.
    - Mutante muerto (Éxito): El test falla $\rightarrow$ la suite sirve.
    - Mutante vivo (Fallo): El test pasa $\rightarrow$ el test es decorativo y no detectó el bug.

### Terminal
```
.\.venv\Scripts\python.exe -m pip install -e ".[dev]"

.\.venv\Scripts\cosmic-ray.exe init cosmic-ray.toml mutation.sqlite

.\.venv\Scripts\cosmic-ray.exe exec cosmic-ray.toml mutation.sqlite

.\.venv\Scripts\cr-report.exe mutation.sqlite | Tee-Object -FilePath MUTATION-REPORT.txt
```

vas a utilizar el prompt 4

## Comparación de prompts

Cuando comparas dos prompts mirando solo un par de salidas, tu cerebro te traiciona. Recuerdas el ejemplo bonito, olvidas el feo y el último que viste pesa más que los demás. Así no se decide nada. La disciplina que le venimos exigiendo a la IA desde el inicio (fijar pruebas, elegir métrica y medir bajo las mismas condiciones) ahora la aplicamos a nuestro propio trabajo.

```
python -m unittest tests.test_refunds_ingenuo -v
python -m unittest tests.test_refunds_original -v
python -m unittest tests.test_refunds -v

cosmic-ray init cosmic-ray-ingenuo.toml mutation-ingenuo.sqlite
cosmic-ray exec cosmic-ray-ingenuo.toml mutation-ingenuo.sqlite
cr-report mutation-ingenuo.sqlite | tee MUTATION-REPORT-INGENUO.txt

cosmic-ray init cosmic-ray-original.toml mutation-original.sqlite
cosmic-ray exec cosmic-ray-original.toml mutation-original.sqlite
cr-report mutation-original.sqlite | tee MUTATION-REPORT-ORIGINAL.txt

cosmic-ray init cosmic-ray.toml mutation-mata-mutantes.sqlite
cosmic-ray exec cosmic-ray.toml mutation-mata-mutantes.sqlite
cr-report mutation-mata-mutantes.sqlite | tee MUTATION-REPORT-MATA-MUTANTES.txt
```

```
Utilizando el contenido de los tres reportes de cosmic-ray [MUTATION-REPORT-INGENUO.txt, MUTATION-REPORT-ORIGINAL.txt y MUTATION-REPORT-MATA-MUTANTES.txt].

Analiza los tres reportes y genera una tabla comparativa siguiendo el siguiente formato:

Suite Mutantes totales Sobrevivientes Relación
Ingenua [valor] [valor] [valor]
Original [valor] [valor] [valor]
Mata mutantes [valor] [valor] [valor]
```

## La IA como supervisor de código
Ahora la IA se va a centrar en juzgar
## Cómo construir un revisor de código con rúbrica

Cuáles son las seis categorías de la rúbrica
Para este ejercicio definimos seis categorías de hallazgo, cada una con su definición clara:

- Corrección: evalúa si el código hace lo que dice. Por ejemplo, en un refund, si actúa correctamente cuando se excede un monto.
- Seguridad: evalúa si se abre una vulnerabilidad, como SQL por concatenación o una autorización ausente.
- Rendimiento: evalúa si escala o se degrada, por ejemplo una consulta muy intensa en la liquidación.
- Tests faltantes: evalúa si el cambio viene o no acompañado de pruebas.
- Estilo: evalúa convenciones, legibilidad, nombres y formatos.
- Documentación: evalúa si los cambios públicos están documentados, como el docstring de un endpoint.

utilizar el prompt 5

## SON validado: cómo un revisor de código
El problema es simple: un revisor que dice "me preocupa que en la línea 42 podría haber un problema de seguridad" está bien para leerlo tú, pero es inservible para un workflow que tiene que decidir solo. Esa ambigüedad de la prosa produce pasos intermitentes, a veces pasan, a veces no, y por razones que nadie controla.

Utilizar el prompt 6

## Rutea code Review
![[assets/image 13.png]]
Utilizar el prompt 7
## Kappa de cohen
Qué mide la concordancia simple y el kappa de Cohen
Al comparar las respuestas de la IA con las respuestas humanas, evalúas dos cosas concretas. Y cada una responde una pregunta distinta.
- La concordancia simple: el porcentaje de casos en que la IA y el humano dijeron lo mismo.
- El kappa de Cohen: te dice si la IA entendió realmente el problema o si solo acertó por puro azar.
![[assets/image 14.png]]
Ejecutar para que te de el formato markdown en script measure_agreement.py

## IA como red team: Romper features con creatividad para encontrar vulnerabilidades antes que un atacante real
Por qué anclar los ataques a OWASP Top 10

Para que un ataque generado por IA sea efectivo, no basta con pedirle que "encuentre fallas". Necesitas un marco. Ahí entra OWASP Top 10, el estándar global de riesgos de seguridad web que permite clasificar los ataques en familias concretas y reproducibles
![[assets/image 15.png]]
Utilizar el prompt 8, lo puedes adaptar a lo que necesitas nos va a ayudar en la documentación y para que nosotros solucionemos ese problema

## Cómo detectar dependencias falsas
El slopsquatting es un vector de ataque que aprovecha las alucinaciones de la IA cuando inventa nombres de paquetes que no existen. Si trabajas con Python y confías en el código generado por IA sin verificar cada dependencia, esta amenaza te afecta directamente. Aquí aprenderás a detectarla y mitigarla antes de que un atacante la explote.

utilizar le prompt 9

## Auditoría de seguridad LLM con OWASP Top 10

Cuando tu código llama a un modelo de lenguaje, el input del usuario puede secuestrar las instrucciones del sistema. Este es el riesgo central al auditar vulnerabilidades en aplicaciones con LLM, un tema clave para desarrolladores que integran endpoints de IA en productos reales como sistemas de soporte.

Un modelo de lenguaje no puede diferenciar de forma confiable lo que le dijo el desarrollador de lo que le está diciendo el usuario. Todo es texto en la misma ventana. Ese es el problema de raíz.

Si el LLM tiene privilegios altos, por ejemplo acceso a datos de cuentas, un usuario con privilegios bajos puede convertirlo en lo que conocemos como confused deputy. En otras palabras, un intermediario confundido que ejecuta acciones que no debería.

Cuáles son las tres vulnerabilidades que debes auditar

La auditoría se centra en tres riesgos concretos que aparecen cuando conectas un modelo a datos sensibles.

El injection vector: determinar si el input del usuario se está concatenando directamente junto al prompt.
El system prompt leak: generar payloads para comprobar si el usuario puede engañar al LLM para que revele sus instrucciones internas completas.
La excessive agency o exceso de agencia: verificar si el LLM tiene más permisos o más herramientas de las que esa función de soporte realmente necesita.

Utilizar el prompt 11