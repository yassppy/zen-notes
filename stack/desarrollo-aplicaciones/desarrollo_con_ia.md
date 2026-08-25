# desarrollo_con_ia
La IA genera código cada vez más rápido, pero sin un marco estricto tiende a inventar cosas, cambiar tu arquitectura o borrar reglas de negocio por su cuenta. La clave está en cómo la diriges.
- Spec-Driven Development (SDD): Le entregas a la IA una especificación clara y detallada (contratos de API, esquemas de BD, reglas de negocio y criterios INVEST). La IA no decide qué hacer, solo implementa estrictamente lo que dictan las especificaciones.
- Vibe Coding Guiado: Programar de forma fluida y conversacional con la IA, pero con "barandillas de seguridad". Tú mantienes el timón técnico para evitar que la IA meta librerías innecesarias o altere el diseño original.

Por qué importa: Si no aplicas SDD o un control firme sobre la IA, terminarás con un código "espagueti" que nadie comprende, lleno de parches inestables y huecos de seguridad.

## Reglas del negocio
Entender la lógica del negocio es decir comprender las reglas
- Ejemplo: Si estás haciendo una app de citas médicas, la regla de negocio es: "Un paciente no puede agendar dos citas con el mismo médico a la misma hora".
- Por qué importa: Si no entiendes esto, le pedirás a la IA "crea un botón para agendar cita" y la IA lo hará, pero sin validar horarios duplicados. El sistema colapsará porque no le diste la regla de negocio.
## Arquitectura
Es la estructura de cómo se conectan las piezas: cómo habla el Frontend con el Backend, cómo se maneja la seguridad, dónde se procesan los pagos y cómo se escalan los servidores.
- Ejemplo: Saber si tu app debe usar microservicios o un monolito, o cómo viaja un token de autenticación (JWT) desde el cliente hasta la base de datos.
- Por qué importa: La IA te da piezas de rompecabezas sueltas. La arquitectura es saber dónde encajar cada pieza para que la app no se caiga cuando entren 10,000 usuarios al mismo tiempo.
## Base de Datos
Es saber cómo estructurar, guardar, relacionar y consultar la información de manera eficiente y segura.
## Testing
Es asegurarte de que el sistema realmente funcione como se espera antes de que los usuarios finales encuentren los errores. Incluye pruebas unitarias, de integración y automatizadas.
## Cloud
Es el entorno donde "vive" tu aplicación para que esté disponible en internet las 24 horas (AWS, Google Cloud, Azure). Involucra servidores, almacenamiento, bases de datos gestionadas y redes.

Resumen:
1. Reglas de Negocio        ➡️ El QUÉ (Las reglas del juego)
2. Arquitectura             ➡️ El CÓMO (El plano y las conexiones)
3. Base de Datos            ➡️ El DÓNDE (La estructura de los datos)
4. Testing                  ➡️ La VALIDACIÓN (Garantía de calidad)
5. Cloud                    ➡️ La INFRAESTRUCTURA (Despliegue al mundo)
6. Desarrollo con IA (SDD)  ➡️ La EJECUCIÓN (Acelerar sin perder el control)

## Recursos
```bookmark
https://syssimulator.com/simulator
```

```bookmark
https://www.youtube.com/watch?v=j0KjVtqoCV0
```

```bookmark
https://www.youtube.com/watch?v=2nEiIG-xca4
```

```bookmark
https://www.youtube.com/watch?v=mFHQ3utAkc8
```


### Arquitectura de 3 capas
![[assets/image 17.png]]





Arquitectura DDD
![[assets/image 16.png]]
 

Para proyectos simples individuales es mejor `estructura por funcionalidades`
- Cuándo se usa: Para prototipos, proyectos personales, startups en etapa inicial o cuando tú eres el único programador.

Proyectos grandes utilizar Clean / Hexagonal Architecture (Puertos y Adaptadores)
- Cuándo se usa: Sistemas bancarios, plataformas de salud, o productos que durarán años y cambiarán de tecnologías constantemente.

Proyectos de empresas grandes y tienes equipos independientes microservicios
- Cuándo se usa: Empresas grandes (tipo Uber, Netflix, Mercado Libre) donde un equipo trabaja en el carrito de compras, otro en los envíos y otro en los pagos.