# 01_entender_finanzas

- Para que aprueben un proyecto debes hablar en el idioma financiero CFO, inversión, retorno y caja.
- Entender que todos que lo que trabajan entiendan como la empresa hace dinero. Identificando las palancas con la que hace dinero.
- Tomar decisiones con datos e IA, siempre preguntarte el porque de las cosas.

## Prompt

### prompt 01
```
Eres mi analista financiero para el curso «Finanzas para no financieros con AI» de Platzi. Trabajamos con el caso de La Tiendita de Platzi, una cadena de 10 supermercados, y más adelante con su negocio nuevo, Tiendita de Platzi a Domicilio.

Cómo quiero que trabajes:

- Responde siempre en español, con tuteo y en lenguaje simple. Explícame sin jerga: si usas un término financiero, defínelo en una frase con un ejemplo del caso.
- Escribe las cifras en USD con punto para miles y coma para decimales (USD 8,35M; 23,8%).
- Antes de calcular, revisa las columnas del archivo que te subo y dime qué supuestos usas.
- Cuando te pida un tablero o un gráfico, créalo como artifact interactivo con los datos incluidos, para que funcione solo.
- Usa los colores de Platzi: verdes #09E989 y #05854D, fondos #F0F5F4 en modo claro y #121413 en modo oscuro; tipografías Bricolage Grotesque para títulos y Plus Jakarta Sans para texto; incluye modo claro y oscuro.
- Termina cada respuesta con la conclusión principal en una frase y, cuando aplique, la decisión que yo debería tomar.
```
### prompt 02
```
Te adjunto el archivo tiendita_platzi_2023_2025.csv con los datos de La Tiendita de Platzi, una cadena de 10 supermercados (enero 2023 a diciembre 2025, en USD sin IVA). Cada fila es un mes de un centro. Las ventas netas de cada tienda son la suma de las columnas que empiezan por "ventas\_" en las filas donde tipo_centro = "Tienda".

Crea un artifact interactivo llamado «Tablero de La Tiendita · v1 Ventas» con:

1. Cuatro indicadores arriba: ventas netas totales de 2025, 2024 y 2023, y el mejor mes.
2. Un gráfico de líneas de las ventas netas mensuales de enero 2023 a diciembre 2025, marcando los diciembres.
3. Un panel con 3 hallazgos en lenguaje simple: en qué mes vende más, cómo cambiaron las ventas de un año a otro y por qué 2025 crece más.

Incluye dentro del artifact los datos que necesites para que funcione solo. Usa los colores de Platzi (verdes #09E989 y #05854D, fondos #F0F5F4 en claro y #121413 en oscuro), tipografías Bricolage Grotesque y Plus Jakarta Sans, y modo claro y oscuro.
```

### prompt 03
```
Mirando el gráfico, explícame en 4 puntos, como si yo no fuera financiero: ¿La Tiendita de Platzi está creciendo?

Dime cuánto crecieron las ventas de 2023 a 2025, por qué diciembre vende tanto y qué le dirías al gerente general en una sola frase.
```

### promp 04
```
La Tiendita de Platzi vendió USD 100,2M en 2025 y su utilidad neta fue USD 1,95M: menos de 2 centavos por cada dólar. Un amigo dice que es un mal negocio porque gana muy poco. ¿Tiene razón?

Explícame en lenguaje simple qué es normal en un supermercado y qué 3 preguntas harías antes de opinar.
```