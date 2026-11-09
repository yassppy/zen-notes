# 02_contexto_numeros

## Reglas a seguir

### Regla 01:
Un número solo no dice nada, se le debe comparar contra algo para darle un contexto.
Ejemplo:
- MON(Mes a mes): 8.13 millones son un crecimiento de 2.7% vs el mes pasado 
![[assets/Pasted Image 2026-11-08 200934.png]]
- YOY: vs el año pasado yo creci 13.6% el ingreso. Si tenia 100 ahora tengo este año 113.6 algo así.
![[assets/Pasted Image 2026-11-08 201206.png]]
- Estoy por debajo del presupuesto 2.5%
![[assets/Pasted Image 2026-11-08 201427.png]]
- Si miro todo el año llevo un 15.6 %
![[assets/Pasted Image 2026-11-08 201645.png]]
## Regla 2: Mide el cambio en dolares y en %
Es importante medir una variación, lo que siempre se estudia en las compañias son variaciones, como les esta llendo vs X.
Formula: (Actual - Base) /Base
![[assets/Pasted Image 2026-11-08 202648.png]]
## Regla 3: Cuando comparas porcentajes
Porcentajes vs puntos porcentuales
Por eso, al leer cualquier cifra, yo preguntaría primero cuál es la base y si el cambio se expresa en puntos o en porcentaje.
![[assets/Pasted Image 2026-11-08 202933.png]]
## Regla 4: Mira el % y los dólares juntos
El efecto base, son importante los valores relativos y los valores de cuanto vendi. No dejarse llevar por que esta empresa esta creciendo pero la base es muy pequeña, esta empresa esta creciendo muy poquito pero la base es muy grande.
![[assets/Pasted Image 2026-11-08 203624.png]]
## Regla 5: El calendario tambien vende
La estacionalidad diciembre engaña
Del ejemplo de la tienda por ejemplo, se nota que se vende menos en enero que diciembre.
Dependiendo del sector comercios diciembre es muy buena temporada de venta y dependiendo del país y me permite evitar tomar decisiones erroneas.
![[assets/Pasted Image 2026-11-08 204317.png]]

## Regla 6: Mira el año completo
Acumulado del año YTD y run rate (Si yo siguiera así que pasaría)
Es recomendable analizar el año completo no dejarme engañar de los picos de ciclos.
![[assets/Pasted Image 2026-11-08 204556.png]]
## Regla 7: Separa lo nuevo de los que ya existia
en retail habren muchas tiendas, misma tienda vs tiendas nuevas

![[assets/Pasted Image 2026-11-08 205018.png]]

## Regla 8: Quitarle la inflación
El crecimiento dominal vs el real
- la inflación es cuánto crecen los precios mes a mes
![[assets/Pasted Image 2026-11-08 205224.png]]
## Regla 9: Separa el tráfico del precio
transacciones vs ticket promedio
La idea es detectar 
![[assets/Pasted Image 2026-11-08 205611.png]]
Del 15% podemos entender que estamos creciendo es por la expanción que hicimos y hay tiendas que no estan creciendo y estamos perdiendo trafico.
![[assets/Pasted Image 2026-11-08 205627.png]]
## Regla 10: importa lo que vendes
En retail es importante conocer esto como esta variando las ventas de estas categorias año a año, como esta variando el margen estoy ganado más dinero o menos dinero.
- Es importante proyectar lo que viene 
![[assets/Pasted Image 2026-11-08 205917.png]]
## Regla 11: Pensar hacia adelante
Tienes que granular es decir descomponer más, se llama sensibilidad
![[assets/Pasted Image 2026-11-08 210223.png]]
## Regla 12: que tanto se mueve el resultado
![[assets/Pasted Image 2026-11-08 210326.png]]

## Regla 13: Batalla contra la inflación
![[assets/Pasted Image 2026-11-08 210520.png]]
## Prompt
### prompt 01
```
¡Entendido! Para agregar las dos pestañas sin romper el tablero original, necesito que adjuntes:

1. El archivo HTML del Tablero de La Tiendita (Clase 1).
2. El archivo CSV `tiendita_platzi_2023_2025.csv`.

No aparecen adjuntos en este mensaje.

Trabajaré sobre el HTML existente, conservaré su diseño y funcionalidades y agregaré únicamente las pestañas COMPARAR y CRECIMIENTO REAL, con todos los cálculos y filtros interactivos que has especificado.
```
### prompt 02
```
Explícame en 5 puntos, como si yo no fuera financiero: ¿a La Tiendita de Platzi le fue bien en 2025?

Primero compara octubre de 2025 contra el mes anterior, contra octubre de 2024 y contra el presupuesto, y dime cuál de las tres comparaciones es la más justa y por qué. Después separa cuánto del crecimiento del año viene de tiendas nuevas, de la inflación y del ticket.

Termina con la decisión que tomarías como gerente: ¿en qué variable pondrías la atención el próximo año y por qué? Y dime qué le dirías al gerente general en una sola frase.
```
### prompt 03
```
El gerente dice: "En enero de 2025 las ventas cayeron 31%, pero cerramos el año creciendo 15%, así que repartamos un bono grande a todos los equipos". ¿Tiene razón?

Revisa las dos frases. En la primera, dime qué comparación engaña y cuánto crecimos realmente en enero. En la segunda, revisa mismas tiendas, inflación y transacciones, y si el crecimiento de la tienda Río es tan bueno como parece.

Dime qué supuesto hay detrás de su decisión y qué le pasaría al EBITDA si el próximo año el ticket cae 5%. Cierra con tu recomendación: ¿aprobarías el bono, no lo aprobarías o lo atarías a alguna meta? ¿Cuál?
```

La pregunta con la que cierra la clase, si las ventas crecieron 6 % y la inflación fue 7 %, tiene respuesta corta: en términos reales no se creció, porque 1,06 sobre 1,07 da cerca de -0,9 %. El tablero con pestaña de crecimiento real automatiza ese descuento, pero el docente advierte que entregar el artefacto sin entenderlo solo perjudica a quien lo hace. Comparto la idea: la herramienta calcula, el criterio sigue siendo suyo. Un ejercicio útil es cambiar la inflación del prompt por la de su país y mirar qué tiendas o líneas pasan a terreno negativo.