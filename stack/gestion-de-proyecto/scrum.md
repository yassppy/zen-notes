# Scrum

Cualquier área puede utilizar **Scrum**: el requisito principal es la **entrega de valor** continua en cada iteración.

## Historia y Evolución

* **Modelo Industrial Tradicional:** Proceso lineal centrado estrictamente en el producto (*Output*). El objetivo principal era producir más rápido.
* **Era Digital:** Transición del enfoque en el producto al **enfoque en el cliente** (*Outcome*). Se busca generar valor agregado mediante el feedback real e iterativo de lo que el cliente realmente necesita.

## ¿Por qué usar Scrum?

Scrum no es solo un conjunto de reglas, es un **marco de trabajo** (lo puedes adaptar a tus necesidades) y una mentalidad basada en la colaboración, la entrega continua, la reflexión y la mejora constante.

### Las 4 Dimensiones de la Agilidad

* **Colaborar:** Trabajar junto a diversas áreas para resolver problemas complejos.
* **Entregar:** Generar y desplegar valor real constantemente.
* **Reflexionar:** Observar cómo interactúan los usuarios con el producto y aprender de los datos/experiencias.
* **Mejorar:** Implementar cambios iterativos para optimizar la eficiencia y el impacto.

## ¿Cuándo utilizar Scrum? (Modelo Cynefin)

El marco de trabajo depende directamente del tipo de problema al que te enfrentas:

| Dominio | Definición | Ejemplo |
| --- | --- | --- |
| **Claro / Simple** | Sigues pasos predeterminados para obtener un resultado predecible. | Ejecutar una Skill o *prompt* estructurado para obtener una redacción final. |
| **Complicado** | Requiere el análisis o la guía de un experto. | Un desarrollador junior integrando un módulo complejo que requiere *code review* de un Senior. |
| **Complejo (Scrum)** | No hay un camino claro; se descubre mediante la **experimentación y prueba**. | Crear un producto con IA donde no sabes si la solución realmente solucionará el problema del usuario. |
| **Caótico** | Se actúa de inmediato para estabilizar la situación antes de analizar. | Un servidor principal caído o un incendio: primero apagas la crisis, luego analizas las causas. |

> **Conclusión:** Scrum es el marco ideal para navegar y prosperar en **dominios complejos**, donde el aprendizaje validado y la adaptación rápida son indispensables.

---

## Valores y Principios para equipos adaptables
![[assets/image 4.png]]

![[assets/image 3.png]]
## Pilares de Scrum
![[assets/image 5.png]]
En resumen: la transparencia nos permite que todo el equipo sea que esta haciendo, la inspección permite probar con el cliente para detectar fallas o mejoras tempranas y la adaptación nos permite corregir las funcionalidades a tiempo para no malgastar tiempo ni dinero.

## Valores de Scrum
![[assets/image 6.png]]
Ejemplo: Un mienbro del equipo tiene un problema dificil que no ha podido resolver solo, la apertura del equipo le da esa oportunidad de discutir y el respeto ayuda a que no se cumple a nadie si no que busquemos la solucción. El enfoque se centra en resolver el problema y el compromiso que todos se compromentan a ayudar para soluccionar.

## 🏈 Scrum Team
Se define la estructura.
El Scrum Team es un equipo pequeño, multifuncional y autoorganizado que comparte un mismo objetivo, todos colaboran con el propósito único de entregar valor de forma incremental. El tamaño ideal para formar al equipo es de 10 personas o menos.
![[assets/image 2.png]]
- Product owner: Maximizar el valor del producto. Conoce las reglas de negocio y sabe qué se quiere desarrollar en base a las necesidades del usuario.
- Scrum master: Velar por la correcta adopción de Scrum y apoyar la efectividad del equipo. Elimina obstáculos que impidan el avance del equipo.
- Developers: Crear un Incremento funcional y utilizable de valor en cada Sprint.

## Eventos tienen 5 Ceremonias o eventos y 3 Artefactos
![[assets/image 11.png]]
### Eventos
Los eventos definen el ritmo
- Sprint: Es un ciclo de entrega, se recomienda de 1 a 2 semanas ya que agregar más semanas puede ser lento.
- Sprint Planning: El equipo define cual es el objetivo del sprint.
- Daily Scrum: Es una inspección diaria de máximo de 15 minutos, pero se recomienda menos. Donde se responde 3 preguntas ¿Qué hice ayer?, ¿Qué voy a hacer hoy? y ¿Estoy bloqueado con algo? recordar que es mala practica solucionar los problemas ahí se debe agendar una reunión con las personas indicadas para no hacer perder tiempo al equipo.
- Sprint Review: Se presenta los resultados obtenidos por cada incremento terminado a stakeholders y negocio. El cliente prueba en vivo. Si algo falla, el equipo sabe qué priorizar en el siguiente Sprint.
- Sprint Retrospective: Oportunidad del equipo para identificar mejoras en su proceso de trabajo.
![[assets/image 12.png]]

### Artefactos
Se define la transparencia
- Product Backlog: Lista ordenada de todos los elementos que hacen parte de ese producto o servicio que se va a construir. 
- Sprint Backlog: Plan pequeño que tendra los desarrolladores durante ese sprint.
- Incremento: Esa porción de producto funcional para el cliente.

## Refinamiento y MoSCoW
El refinamiento no es un evento, es una actividad continua donde el product owner junto al equipo de desarrolladores lo dividen en partes pequeñas para que sean más entendibles.
Por ello, se utiliza la técnica MoSCoW:
- Must have: Lo vital, `tiene que estar si o si`. Sin esto, la app no sirve para nada y no podemos lanzarla al mercado.
- Should have: Es súper importante y agrega mucho valor, pero si no se llega a tiempo, la app igual puede operar. `Puede operar aunque no este`
- Could have: El "gustito" `opcional` si nos sobra tiempo y presupuesto.
- Won’t have: Ideas geniales que conscientemente `dejamos fuera` del primer lanzamiento para no perder tiempo ni dinero

MoSCoW nos va a ayudar a `priorizar que historias de usuario` se contruye primero para sacar el producto mínimo viable (MVP) en cada Sprint.

Para comprenderlo mejor vamos a poner un ejemplo estamos creando una app de viajes.

- Épica principal: Tenemos una funcionalidad o meta gigante que no puede entrar en un Sprint para eso se necesita dividirlo en partes más pequeñas. Como la Gestión de reservas que me permita buscar y reservar
- Descomposición: Lo dividimos en historias de usuarios más pequeñas.

HU-1: Como viajero, quiero buscar alojamientos por destino y fecha, para encontrar opciones disponibles. `Must have`
HU-2: Como viajero, quiero confirmar la reserva y ver el resumen del pago, para asegurar mi hospedaje.`Must have`
HU-3: Como viajero, quiero filtrar búsquedas por precio y rango de estrellas, para encontrar opciones según mi presupuesto.`Should have`
HU-4: Como viajero, quiero guardar alojamientos en una lista de "Favoritos", para revisarlos más tarde. `Could have`
HU-5: Como viajero, quiero dividir el costo de la reserva directamente entre varias tarjetas de mis amigos, para pagar en grupo. `Won't Have`

Te preguntaras como priorizar:
- Los Must Have forman tu Release 1 (MVP).
- Los Should Have van para los siguientes Sprints.
- Los Could y Won't Have se quedan al final del Backlog.

## Historia de usuario e INVEST
Las Historias de Usuario no son contratos aburridos, son conversaciones para dar valor real es decir son la descripción de `una necesidad desde la prespectiva del usuario final`.
- El Formato: Como `Rol` + Quiero `Función, que acción quiere realizar` + Para `Beneficio`.
- El Checklist INVEST: Deben ser Independientes, Negociables, Valiosas, Estimables, Small (pequeñas para entrar en un sprint) y Testeables.

Esto queda más claro con ejemplos:
- MALO: Como desarrollador, quiero crear una tabla en PostgreSQL para guardar los datos.

BUENO:

Ejemplo en SALUD
- Como paciente con horario de trabajo ocupado,
- Quiero ver la lista de turnos médicos disponibles ordenados por fecha y hora,
- Para agendar una consulta en menos de 3 minutos sin tener que llamar por teléfono.
Ejemplo en E-commerce
- Como comprador frecuente,
- Quiero guardar mi tarjeta de crédito de forma segura en mi perfil,
- Para pagar mis compras futuras con un solo clic sin reingresar mis datos.
Ejemplo en Educación
- Como estudiante que viaja seguido en metro,
- Quiero descargar mis lecciones en el celular para verlas sin conexión a internet,
- Para no interrumpir mi estudio durante mis trayectos.

Ahora, para saber que la historia esta realmente terminada:

### Criterios de Aceptación: ¿Qué debe hacer esta función específica? (Únicos por historia)
Son las condiciones únicas que debe cumplir esa historia en particular para que el Product Owner la acepte. Describen el comportamiento o resultado esperado de la funcionalidad.

Ejemplo para Agendar Cita:
- Debe permitir elegir fecha y hora.
- Debe enviar un correo de confirmación al terminar.
- Debe garantizar la consistencia de datos (no permitir doble reserva en el mismo horario).

### Definición de Terminado / Definition of Done: ¿Tiene la calidad técnica necesaria para ir a producción? (Igual para todas las historias)
Es el estándar de calidad formal que debe cumplir cualquier historia antes de poder presentarse en la Sprint Review. Aplica para todo el proyecto y busca mantener la disciplina técnica.

Ejemplo global para todas las historias:
- El código fue revisado por otro desarrollador (Code Review).
- Se realizaron las pruebas unitarias solamente enfocadas en el negocio.
- No hay errores críticos de seguridad.
- La documentación técnica fue actualizada.

### Creación de subtareas para el equipo
Todo el avance entre el backend, frontend y QA se centraliza en esa misma historia de usuario
- 🛠️ [Dev Backend]: Crear el endpoint API en Node.js para autenticación.
- 🛠️ [Dev Frontend]: Diseñar la pantalla de Login en React con los campos de texto.
- 🛠️ [QA / Tester]: Ejecutar pruebas de seguridad contra ataques de inyección SQL en esas mismas ramas.

Cada desarrollador trabaja en la rama de su respectivo repositorio usando el código de la Historia de Usuario:

Repositorio mi-app-backend:
- El dev de Backend crea la rama: feature/HU01-auth-api
- Trabaja el endpoint, encriptación y base de datos.
- Sube su código.

Repositorio mi-app-frontend:
- El dev de Frontend crea la rama: feature/HU01-login-ui
- Diseña la pantalla y conecta el formulario consumiendo la API de Backend.
- Sube su código.

## Estimación Relativa y Planning Poker
Normalmente se utiliza esto https://planningpokeronline.com/ pero puedes crear en base a tus preferencias

Olvídate de estimar en horas exactas. Aquí usamos estimación relativa con la serie de Fibonacci tomando un pivote de referencia (ejemplo: un Zorro = 3; un Elefante = 20).

¿Cómo se juega al Planning Poker? El PO presenta la historia, el equipo aclara dudas, cada dev vota una carta en secreto, se revelan al mismo tiempo y se debaten las diferencias extremas hasta llegar a un consenso.

## User Story Map y Planeación del Release
El User Story Map es el puente visual entre la visión del producto y el backlog. Se organiza por:
1. Usuarios $\rightarrow$ 2. Actividades $\rightarrow$ 3. Tareas $\rightarrow$ 4. Historias de Usuario $\rightarrow$ 5. Releases/Sprints.

Plan de Ataque para el PMV:
- Sprint 1 (Registro y login): Registro/Login, Base de Datos y API JWT. (12 SP)
- Sprint 2 (Búsqueda): Disponibilidad médica y Buscador por especialidad. (16 SP)
- Sprint 3 (Reserva): Agendar cita MVP y Confirmación por email. ¡Flujo completo listo! (13 SP)

Recursos:

```bookmark
https://www.mural.co/templates/user-story-map
```
```bookmark
https://miro.com/es/plantillas/mapa-historia-de-usuario/
```
```bookmark
https://miro.com/templates/user-story-map-con-ejemplos/
```
```bookmark
https://www.notion.com/es/templates/category/kanban
```


![[assets/image 10.png]]

![[assets/image 9.png]]
## Medir lo que Importa: Métricas y Valor
Un incremento entregado debe cumplir con la Definición de Terminado (DoD) para garantizar calidad y transparencia. Para saber si triunfamos, miramos las métricas correctas:

- Métricas de Flujo (Proceso): Throughput (ritmo de entrega) y Lead Time (tiempo de inicio a fin).
- Métricas de Resultado (Outcome): Como el NPS (satisfacción del cliente).
- Métrica Estrella de SaludTech: Tiempo Promedio para Asegurar una Cita (bajando el tiempo de espera de 7 a 3 días).