# clase03_ia_generativa
## ¿Qué son los modelos funcionales?
- Son modelos entrenados con datos a escala de internet.
- La diferencia con el machine learning tradicional donde se entrena un solo modelo para una tarea específica, el FM se adapta a un solo modelo para realizar multiples tareas.
- Tareas que realiza:
    - Generación y resumen de texto.
    - Extracción de información y respuestas a preguntas.
    - Generación de imágenes e interacciones con chatbots.
    - Sirven como punto de partida para desarrollar modelos más especializados.

## Ciclo de Vida de los FM
- Selección de datos: El FM requiere de datos sin etiquetar por que son más fácil de conseguirlo, esto puede incluir datos sin procesar, imagenes, archivo de texto o video.
- Entrenamiento: Se entrena principalmente mediante aprendizaje autosupervisado (el modelo genera sus propias etiquetas usando la estructura de los datos) aprendiendo sobre el contexto y las relaciones de las palabras (preentrenamiento inicial). Luego de eso el modelo puede decidir si sigue entrenando con datos adicionales (A todo eso se le conoce como  entrenamiento previo continuo).
- Optimización: Se adapta el modelo mediante técnicas como Ingeniería de Peticiones (Prompt Engineering), RAG (Generación Aumentada por Recuperación) o ajuste con datos específicos de tareas.
- Evaluación: Se mide el rendimiento del modelo utilizando métricas y puntos de referencia (benchmarks) para asegurar que satisface las necesidades del negocio.
- Implementación: Una vez que cumple con los criterios de rendimiento, el FM se lleva a producción integrándolo en aplicaciones, APIs o sistemas de software.
- Retroalimentación y mejora continua: Se monitorea el rendimiento tras la implementación y se recopilan opiniones de usuarios y expertos para detectar sesgos. Se relizan ajustes al modelo continuamente.

## Amazon Bedrock
- Es el servicio que da acceso a una selección de FM de alto rendimiento creados por empresas líderes en IA y por Amazon.
- Empresas aliadas: AI21 Labs, Anthropic, Cohere, Meta, Mistral AI, Stability AI y Amazon.

## Modelos de lenguaje grande (LLM)
Se basa en una gran cantidad de arquitecturas, lo más actual es la arquitectura de transformadores.
- Son modelos útiles que puedes entender y generar texto similar al humano.
- Están entrenados con una gran cantidad de datos de diferentes fuentes de internet, libro y otras fuentes.
![[assets/image 21.png]]
## Tokens
- El LLM necesita cortar tu texto en pedazos manejables a eso se le llama tokenización.
- Puede ser palabras, frases o caracteres individuales como un punto depende de la empresa ChatGPT lo divide de diferente a Google.
![[assets/image 22.png]]
## Integración y vectores
- La integración son representaciones númericas de los tokens, en las que cada token se le asigna un vector y captura la relación que tienen esos tokens. Permitiendo que el modelo comprenda el contexto y las matrices del lenguje.
- Esto se basa en la similitud del coseno midiendo que tan parecidos son dos vectores para entender la relación semantica entre las palabras.
![[assets/image 23.png]]
Los LLM utilizan estos tokens, integraciones y vectores para comprender y generar texto. Estos modelos pueden captar relaciones complejas de modo que puede generar texto coherente y apropiado para el contexto, responder pregruntas, resumir.

## Difusión directa
Mediante la difusión directa, el sistema introduce gradualmente una pequeña cantidad de ruido en una imagen de entrada hasta que solo queda el ruido.

![[assets/image 24.png]]
## Difusión inversa
En la etapa de difusión inversa subsiguiente, la imagen ruidosa se introduce gradualmente en la eliminación del ruido hasta que se genera una nueva imagen.
![[assets/image 25.png]]
Las aplicaciones más conocidas han sido modelos de conversión de texto a imagen, los modelos de difusión se pueden aplicar a una variedad de tareas más allá de la simple generación de imágenes.

## Modelo multimodales
Pueden procesar varios modos de datos simultáneamente en la salida, se podría enviar una imagen y el texto de entrada, a continuación, se generara una nueva imagen y un título. Se utiliza para:
- Automatizar los subtítulos de video.
- Responder preguntas de forma más visual utilizando graficos visuales y texto.
- Traducir contenido en las imagenes.

## Redes generativas antagónicas (GAN)
Modelo de IA que utiliza dos redes neuronales que compiten entre sí para generar datos artificiales que parezcan reales. Su objetivo es produce datos que no se pueden distinguir de los datos reales.
- Generador: crea datos falsos (imágenes, texto o audio) a partir de ruido aleatorio. Su objetivo es generar datos que parezcan reales.
- Discriminador: analiza los datos reales y los generados para intentar distinguir cuáles son auténticos y cuáles son falsos.
- Entrenamiento: ambas redes mejoran mediante la competencia. El generador intenta engañar al discriminador, mientras que el discriminador aprende a detectar los datos falsos.

## Codificadores automáticos variacionales (VAE)
modelo generativo de IA que aprende las características principales de los datos para reconstruirlos y generar nuevos datos similares
- Codificador (Encoder): comprime los datos de entrada, como una imagen, en una representación más pequeña llamada espacio latente representación matematica mediante valores númericos, que conserva sus características importantes.
- Decodificador (Decoder): utiliza una representación del espacio latente para reconstruir los datos originales o generar datos nuevos similares.
- Generación de datos: el modelo toma muestras aleatorias del espacio latente y las pasa por el decodificador para crear nuevos datos.

## Optimización del resultado del modelo
Un FM se puede optimizar aún más de varias maneras diferentes. Estas técnicas varían en complejidad y costo, y la opción más rápida y económica es la **ingeniería de peticiones**.

Ingeniería de peticiones:
Brindar una manera de guiar el comportamiento del modelo hacia los resultados que quiere lograr.

- Instrucciones: Esta tarea la debe realizar el FM. Proporciona una descripción de la tarea o una instrucción sobre cómo debe funcionar el modelo.
- Contexto: Información externa que sirve de guía para el modelo.
- Datos de entrada: La entrada para la que se desea una respuesta.
- Indicador de salida: El tipo o formato de salida.

## Ajuste de modelos de IA (Fine-tuning)
Proceso de adaptar un modelo de IA previamente entrenado utilizando datos más específicos para mejorar su rendimiento en una tarea determinada.
- Refinamiento de las instruciones: usa ejemplos de cómo el modelo debe responder a una instrucción específica.
- RLHF (aprendizaje por refuerzo a partir de retroalimentación humana): técnica que utiliza las preferencias y evaluaciones humanas para orientar las respuestas del modelo hacia lo que las personas consideran más útil o adecuado.

## Generación aumentada por recuperación (RAG)
técnica que busca información relevante en documentos o fuentes de datos de la empresa y se la proporciona a un modelo de IA como contexto para generar respuestas más precisas.

Diferencias: RAG le da información al modelo para que la consulte, mientras que Fine-tuning lo entrena para que aprenda a realizar mejor una tarea.

