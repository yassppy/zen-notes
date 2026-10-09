# clase02_deep_learning

## Aprendizaje profundo (Deep Learning)

Esta inspirado en como funciona el cerebro, es especial sobre la neurona artifical diseñado para imitar la forma en que el humano procesa la información.

## Concepto de neurona artificial
En esta parte entendemos como funciona la neura del ser humano
- Dendritas(Representa la entrada): Recibe señales o impulsos eléctronicos de otras neuronas. En deep learning esto equivale a las entradas de datos.
- El Axón o cuerpo celular (Procesamiento y disparo): El pulso viaja a través del cuerpo de la neurona hasta la parte terminal. Si la señal acumulada supera cierto límite, la neurona "se dispara" y transmite la información. En la inteligencia artificial, esto se modela mediante pesos, sesgos y funciones de activación (que deciden si la neurona pasa la señal a la siguiente capa o no).
- Las Terminales del Axón (Salida / Conexión): Se conectan con las dendritas de la siguiente neurona para hacer fluir la información. En el modelo matemático, esto representa la propagación de la señal hacia las capas ocultas y de salida de la red neuronal.
![[assets/image 19.png]]

## Como se representa en forma matematica
Recordar que se representa en una matriz
- Toma valores de entrada (X)
- Los pesos (W) de los valores indican que tan importante es cada entrada.
- Realiza una operación de producto matricial multilpicando cada entrada por su peso y luego se suma todo.
- luego decide si el resultado es suficiente para activarse o no según un umbral.

## Las capas 

Estos nodos se organizan en capas, la capas incluyen una capa de entrada, una o más capas ocultas y una capa de resultados.
![[assets/image 20.png|436]]
Funciona muy bien cuando mostramos muchos ejemplos a una red neuronal, como datos de clientes que compraron cierto productos, identifica patrones ajustando su conexiones entre nodos y descubrieran los patrones de los diferentes clientes y hacer prediciones de lo que podría comprar para enviarle publicidad sobre productos especificos.

Visión artificial:
- Un campo de la inteligencia artificial que hace posible que las computadoras interpreten y comprendan videos e imágenes digitales. El aprendizaje profundo ha revolucionado este campo ya que proporciona técnicas para la clasificación de imagenes, detección de objetos y la segmentación de imagenes.

Procesamiento de lenguje natural (NLP):
- Es una rama de la IA que se ocupa de la interación entre las computadoras y los lenguajes humanos. El aprendizaje profundo ha logrado avances significativos en el NLP, permite la clasificación de texto, el análisis de sentimiento, la traducción automática y la generación del lenguaje.

