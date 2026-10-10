# clase04_infraestructura_aws

Se aprendera sobre los distintos servicios de IA y ML disponibles en AWS.

## Pila de servicios de AI/ML de AWS
![[assets/image 26.png]]
## Marcos de trabajao en ML
Ahora se le conoce como Amazon SageMaker AI una capa de marco de trabajo, ofrece herramientas para crear, entrenar y ejecutar LLM u otros FM de forma eficiente sin tener que administrar toda la infraestructura con el menor esfuerzo posible.
- Simplifica las tareas de infraestructura.

## Servicio de IA y machine learning
Ofrece soluciones que están listas para usar que no se requiere una amplia administración de infraestructura ni experiencia especializada.
![[assets/image 27.png]]
## Servicios de IA y Machine Learning de AWS

### Servicios para trabajar con texto

- **Amazon Comprehend — Análisis de texto:** Utiliza ML y procesamiento de lenguaje natural (NLP) para analizar textos no estructurados y extraer información útil.
  - Ejemplo: «Compré una laptop en Lima y llegó excelente, pero el envío fue muy lento».
  - Sentimiento = Mixto, opinión positiva sobre el producto y negativa sobre el envío.
  - Entidad = Lima.
  - Frases clave = `compré una laptop` y `envío muy lento`.
  - Idioma = Español.

- **Amazon Translate — Traducción automática:** Utiliza modelos de aprendizaje profundo para traducir textos entre diferentes idiomas de forma natural.
  - Ejemplo: traducir una página web del español al inglés.
  - Entrada = `Hola, ¿cómo estás?`
  - Traducción = `Hello, how are you?`
  - Idea clave = Traducir un idioma a otro.

### Servicios para trabajar con documentos

- **Amazon Textract — Extracción de datos:** Extrae automáticamente texto, campos de formularios y tablas de documentos escaneados. Va más allá del OCR tradicional, que reconoce caracteres.
  - Ejemplo: procesar un comprobante de pago.
  - Texto = `Total: S/ 45.50`
  - Dato extraído = Importe: `45.50`
  - Idea clave = Extraer texto y datos de documentos.

### Servicios para trabajar con ChatBots

- **Amazon Lex — Bots conversacionales:** Permite crear chatbots y asistentes que interactúan con las personas mediante texto o voz. Reconoce lo que dice el usuario y la intención de su mensaje.
  - Ejemplo: un chatbot para consultar pedidos.
  - Usuario = «¿Dónde está mi pedido?»
  - Intención = Consultar estado del pedido.
  - Respuesta = «Tu pedido está en camino».
  - Idea clave = Crear asistentes conversacionales.

### Servicios para trabajar con voz

- **Amazon Polly — Texto a voz (TTS):** Convierte texto escrito en voz sintética que suena natural.
  - Ejemplo: una aplicación que lee un artículo en voz alta.
  - Entrada = `Bienvenido a nuestra aplicación`.
  - Salida = Audio que pronuncia esa frase.
  - Idea clave = Texto → Voz.

- **Amazon Transcribe — Voz a texto (ASR):** Convierte automáticamente el audio hablado en texto y puede generar marcas de tiempo.
  - Ejemplo: transcribir una reunión grabada.
  - Entrada = Audio de una reunión.
  - Salida = Texto con lo que dijeron los participantes.
  - Uso = Crear subtítulos, transcribir llamadas y analizar conversaciones.
  - Idea clave = Voz → Texto.

### Servicios para trabajar con visión

- **Amazon Rekognition — Análisis de imágenes y videos:** Utiliza aprendizaje profundo para identificar objetos, personas, texto, escenas y determinadas actividades en imágenes y videos. También ofrece funciones de análisis facial.
  - Ejemplo: analizar una fotografía de una calle.
      - Objetos detectados = Automóviles, personas y señales.
  - Texto detectado = Palabras visibles en una señal.
  - Idea clave = Analizar imágenes y videos.

### Servicios para buscar información

- **Amazon Kendra — Búsqueda inteligente:** Utiliza ML para ayudar a encontrar información relevante dentro de documentos y repositorios de una organización.
  - Ejemplo: una empresa tiene miles de documentos y un empleado busca «política de vacaciones».
  - Resultado = Documentos relevantes que contienen información sobre las vacaciones.
  - Idea clave = Buscar información entre muchos documentos.

### Servicios para realizar recomendaciones

- **Amazon Personalize — Recomendaciones personalizadas:** Utiliza datos de actividad de los usuarios, como visitas y compras, para generar recomendaciones adaptadas a sus intereses.
  - Ejemplo: una tienda en línea registra que un usuario compra libros de programación.
  - Datos = Historial de compras y productos consultados.
  - Resultado = Recomendar otros libros de programación.
  - Idea clave = Recomendar contenido según los intereses del usuario.

### Servicio para Miscelánea (aprender mediante recompensas)

- **AWS DeepRacer — Aprendizaje por refuerzo (RL):** Es una plataforma educativa basada en un auto de carreras a escala que permite experimentar con modelos que aprenden mediante recompensas.
  - Ejemplo: entrenar un auto virtual para recorrer una pista.
  - Acción = El auto toma una decisión, como girar.
  - Recompensa = Recibe una señal según qué tan bien se comporta.
  - Aprendizaje = Ajusta su comportamiento para mejorar su rendimiento a largo plazo.
  - Idea clave = Aprender mediante acciones y recompensas, sin necesitar ejemplos etiquetados para cada acción.

## IA generativa — Servicios de AWS
- Amazon SageMaker JumpStart — Inicio rápido con modelos de ML: ofrece modelos preentrenados, soluciones y plantillas para acelerar el desarrollo de proyectos de Machine Learning. Permite implementar y ajustar modelos compatibles.
    - Ejemplo: quieres crear un sistema que clasifique imágenes, pero no quieres comenzar desde cero.
    - Herramienta: eliges un modelo preentrenado y lo implementas para comenzar a probarlo.
    - Idea clave: acelerar el inicio de proyectos de ML con modelos y soluciones existentes.
- Amazon Bedrock — Acceso a modelos fundacionales (FM): servicio administrado que permite utilizar diferentes modelos fundacionales mediante una API, personalizarlos y conectarlos con aplicaciones.
    - Ejemplo: quieres crear un asistente que responda preguntas sobre comprobantes de pago.
    - Herramienta: conectas tu aplicación con un modelo de IA mediante Bedrock para interpretar descripciones y generar respuestas.
    - Idea clave: utilizar modelos de IA generativa desde una API sin tener que administrar directamente toda su infraestructura.
- Amazon Q — Asistente de IA empresarial: ayuda a encontrar información, responder preguntas, generar contenido y resolver tareas utilizando información de los sistemas y repositorios empresariales a los que tiene acceso.
    - Ejemplo: un empleado necesita encontrar una política interna entre muchos documentos de su empresa.
    - Resultado: Amazon Q puede ayudarle a localizar la información y responder su pregunta.
    - Idea clave: utilizar IA para consultar información y facilitar el trabajo empresarial.
- Amazon Q Developer — Asistente de programación: ayuda a los desarrolladores a escribir, comprender y mejorar código mediante recomendaciones y generación de código con IA.
    - Ejemplo: estás desarrollando una API en Laravel y necesitas implementar una función para registrar usuarios.
    - Resultado: el asistente puede sugerir código y ayudarte a comprender cómo funciona.
    - Idea clave: utilizar IA para acelerar el desarrollo de software.
## Ventajas y beneficios de las soluciones de IA de AWS
- Permite desarrollo más rápidos
- Las empresas pagan por los recursos que consumen y permite que aplicaciones escalen sin problema.
- Ofrece una alta gama de herramientas para que los desarrolladores puedan incorporar a sus aplicaciones.
## Consideraciones sobre los costos

Es importante evaluar cuidadosamente sus requisitos y cargas de trabajo específicos a la hora de elegir los servicios de AWS. Factores como los enumerados anteriormente pueden tener un impacto significativo en el costo y el rendimiento generales.

- Capacidad de respuesta y disponibilidad: obtener respuestas más rápidas y `mantener el servicio disponible durante más tiempo puede aumentar los costos`.
    - Ejemplo: una aplicación que necesita responder en milisegundos puede requerir una infraestructura más costosa.
    - Idea clave: mayor rapidez y disponibilidad pueden significar mayor costo.
- Redundancia y Cobertura regional: consiste en distribuir recursos en varias zonas de disponibilidad o regiones para reducir el riesgo de interrupciones. `Genera un mayor costo debido a que deben replicar los recursos en varias ubicaciones`.
    - Ejemplo: si una región de AWS falla, otra puede seguir atendiendo las solicitudes, si la arquitectura está preparada para ello.
    - Idea clave: más copias y ubicaciones aumentan la resiliencia, pero también los costos.
- Rendimiento y capacidad de cómputo: AWS ofrece recursos como CPU, GPU y aceleradores especializados. Los recursos más potentes suelen ser más costosos cuando se utiliza el GPU.
    - Ejemplo: entrenar un modelo grande con GPU puede ser más rápido que hacerlo con CPU, pero puede costar más.
    - Idea clave: mayor capacidad de cómputo puede mejorar el rendimiento y aumentar el precio.
- Precios basados en tokens: algunos servicios, como Amazon Bedrock, cobran según el uso de tokens de entrada y salida, dependiendo del modelo y de la modalidad de precios.
    - Ejemplo: enviar un texto largo y generar una respuesta extensa suele consumir más tokens que una pregunta breve.
    - Idea clave: más tokens procesados o generados pueden significar mayor costo.
- Rendimiento aprovisionado: consiste en reservar capacidad de procesamiento por adelantado para atender una carga de trabajo de forma más predecible.
    - Ejemplo: una empresa reserva capacidad para procesar muchas solicitudes durante todo el día.
    - Idea clave: reservar más capacidad puede aumentar el costo, incluso si no se utiliza por completo.
- Modelos personalizados: entrenar o adaptar modelos y desplegarlos puede generar costos adicionales de cómputo, almacenamiento y preparación de datos.
    - Ejemplo: adaptar un modelo para comprender términos específicos del sector financiero.
    - Idea clave: personalizar un modelo puede mejorar su utilidad, pero requiere recursos adicionales.