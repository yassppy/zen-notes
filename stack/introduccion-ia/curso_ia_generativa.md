# 🧠 IA Generativa — Resumen de estudio

## 1. ¿Cómo funciona la IA generativa?

* La IA generativa **predice qué palabra o elemento debería venir después** usando patrones estadísticos aprendidos durante su entrenamiento.
* No significa que "sepa" la verdad.
* Puede:
  * cometer errores, arrastrar sesgos e inventar información con mucha seguridad.
* Por eso necesitamos un **filtro humano antes de utilizar su respuesta**.

---

# 🚦 2. Técnica del semáforo para IA

Sirve para decidir:

> **¿Cuánta confianza puedo depositar en la IA para esta tarea?**

### 🟢 Verde — Delegar

* El error tiene consecuencias pequeñas.
* Puedes revisar/corregir rápidamente.
* La IA puede hacer gran parte del trabajo.

**Ejemplos:**

* Redactar un correo.
* Generar ideas.
* Ordenar apuntes.
* Crear un script de prueba.
* Generar expresiones regex para experimentar.

**Ejemplo Data Engineering:**

```text
Crea una regex para detectar códigos UBIGEO inválidos.
```

Si falla → estás haciendo una prueba → corriges y continúas.

---

### 🟡 Amarillo — IA + revisión humana

* El error puede causar problemas.
* La IA puede ayudarte bastante.
* **La revisión humana es obligatoria.**

**Ejemplo:**

```text
Analiza las ventas de este dataset y calcula el crecimiento mensual.
```

La IA puede hacer el análisis, pero debes comprobar:

* datos utilizados.
* cálculos.
* filtros.
* resultados.

> 🟡 **La IA hace el trabajo pesado; tú haces control de calidad.**

---

### 🔴 Rojo — Decisión humana

* Un error puede causar consecuencias graves.
* Es difícil deshacer el daño.
* La IA puede servir como apoyo, pero necesitas una **fuente de verdad** y criterio humano.

**Ejemplos:**

* Ejecutar cambios destructivos en producción.
* Diagnóstico médico.
* Decisiones legales.

---

## 🧩 Regla sencilla

| Color       | Pregunta                                                     |
| ----------- | ------------------------------------------------------------ |
| 🟢 Verde    | ¿Si falla, puedo corregirlo fácilmente?                      |
| 🟡 Amarillo | ¿Si falla, puede causar problemas pero puedo revisarlo?      |
| 🔴 Rojo     | ¿Si falla, puede causar un daño serio o difícil de revertir? |

---

# 🧠 3. Descomponer problemas

El problema:

> **No deberías lanzarle a la IA un problema gigante y desordenado esperando una respuesta específica.**

La IA responde según el **nivel de detalle que le das**.

Por eso:

```text
Problema desordenado
        ↓
Listar
        ↓
Agrupar
        ↓
Conectar
        ↓
Priorizar
        ↓
Prompt claro
        ↓
Respuesta útil
```

El material de la clase plantea precisamente usar estos cuatro movimientos antes de escribir el prompt y luego comprobar la descomposición con tres señales de calidad. 

---

# 1️⃣ Listar — Vaciar la cabeza

* Escribes **todo lo que podría estar relacionado con el problema**.
* No importa si está desordenado.
* No juzgas todavía qué es importante.

### 👨‍💻 Ejemplo

Problema:

> "Mi pipeline de datos está fallando."

Lista:

* PostgreSQL lento.
* CSV tiene datos incorrectos.
* Python tarda mucho.
* Hay duplicados.
* La API falla.
* No sé dónde ocurre el error.
* La tabla tiene muchos registros.
* El script no tiene logs.

👉 Todavía **no solucionamos nada**. Solo estamos sacando información de la cabeza.

La guía de la clase indica justamente describir primero el problema tal como lo tienes en la cabeza y luego listar sin filtrar lo que podría estar alimentándolo. 

---

# 2️⃣ Agrupar — Encontrar categorías

Ahora buscamos cosas que pertenecen al mismo tema.

### Ejemplo

**Datos**

* CSV incorrecto.
* Duplicados.

**Base de datos**

* PostgreSQL lento.
* Tabla grande.

**Código**

* Python tarda mucho.
* Script sin logs.

**Infraestructura/API**

* API falla.

👉 Pasamos de:

```text
8 problemas desordenados
```

a:

```text
Datos
Base de datos
Código
Infraestructura
```

La idea de la clase es dejar que los elementos se agrupen y ponerles un nombre lógico. 

---

# 3️⃣ Conectar — Encontrar qué causa qué

Este es uno de los pasos más importantes.

Pregúntate:

> **¿Qué está provocando qué?**

Ejemplo:

```text
CSV incorrecto
      ↓
Datos duplicados
      ↓
Más registros en PostgreSQL
      ↓
Consulta más lenta
      ↓
Pipeline tarda demasiado
```

Ahora descubriste algo importante:

> El problema aparentemente era "PostgreSQL lento", pero podría comenzar mucho antes, en los datos de entrada.

La clase enfatiza precisamente buscar qué grupo está empujando a otro y qué elementos que parecían separados realmente están relacionados. 

---

# 4️⃣ Priorizar — Elegir una sola cosa

No intentes arreglar todo al mismo tiempo.

Pregúntate:

> **Si solo pudiera solucionar una cosa esta semana, ¿cuál sería?**

Ejemplo:

❌

```text
Voy a optimizar Python,
PostgreSQL,
la API,
el CSV,
los logs...
```

✅

```text
Primero voy a comprobar la calidad del CSV.
```

¿Por qué?

Porque si los datos de entrada están mal, optimizar PostgreSQL podría no solucionar el problema real.

La plantilla de la clase plantea exactamente elegir **una cosa** para atacar primero y explicar por qué. 

---

# ✅ 4. Las 3 señales de una buena descomposición

Antes de preguntarle a la IA, revisa:

### 1. Distintas

Cada grupo representa algo diferente.

```text
Datos ≠ Código ≠ Base de datos
```

No debes repetir la misma idea con nombres diferentes.

### 2. Completas

Entre todos los grupos deben cubrir el problema.

```text
Datos
Código
BD
Infraestructura
```

No debería faltar una pieza importante.

### 3. Conectadas

Debes entender la relación:

```text
Datos → Código → BD → Resultado
```

No quieres simplemente tener una lista bonita; quieres saber **cómo se relacionan las piezas**.

Estas tres señales —distintas, completas y conectadas— son las que utiliza la plantilla de la clase para validar la descomposición. 

---

# 🤖 5. Ahora sí: escribir el prompt

Después de ordenar el problema, recién hablamos con la IA.

En lugar de:

```text
¿Por qué mi pipeline está lento?
```

Le damos contexto:

```text
Soy Data Engineer.

Tengo un pipeline que recibe un CSV,
procesa los datos con Python y los almacena
en PostgreSQL.

El pipeline está tardando demasiado.

Después de analizar el problema encontré que
el CSV contiene muchos duplicados y esto aumenta
la cantidad de registros que llegan a PostgreSQL.

Quiero que me ayudes a determinar si esta
es realmente la causa principal y qué pruebas
puedo realizar antes de modificar el pipeline.

No quiero todavía una solución definitiva;
quiero un plan de diagnóstico paso a paso.
```

🔥 **La diferencia importante:**

```text
❌ Problema → IA → respuesta genérica

✅ Problema
      ↓
   Descomponer
      ↓
   Entender relaciones
      ↓
   Priorizar
      ↓
   IA → respuesta específica
```

La plantilla de la clase pide que el prompt final incluya quién eres, qué ocurrió, qué encontraste al conectar las piezas y qué necesitas exactamente. 

---

# 🧠 Resumen

Si mañana tuvieras que explicárselo a alguien:

> **Antes de pedirle a la IA que resuelva un problema, primero ordeno mi propio pensamiento.**

```text
LISTAR
↓
¿Qué cosas están involucradas?

AGRUPAR
↓
¿A qué categoría pertenece cada cosa?

CONECTAR
↓
¿Qué causa o afecta a qué?

PRIORIZAR
↓
¿Qué voy a solucionar primero?

VALIDAR
↓
¿Mis grupos son distintos, completos y conectados?

PROMPT
↓
Ahora sí le doy el contexto a la IA.
```

### 🎯 Para recordarlo fácilmente

> **No le entregues tu caos a la IA esperando que ella haga todo el pensamiento. Primero convierte el caos en estructura.**


## 🧠 Identificar la causa raíz antes de pedir ayuda a la IA

## 💡 Idea principal

La mayoría de veces el problema no es:

```text
"La IA respondió mal"
```

El problema real es:

```text
"Le expliqué el síntoma, no la causa raíz."
```

> **Mejor problema → Mejor respuesta de la IA.**

---

# 🧩 Los 3 niveles

Cuando algo falla, existen tres capas:

```text
👀 Síntoma
↓
⚙️ Causa
↓
🌳 Causa raíz
```

| Nivel         | Pregunta                       |
| ------------- | ------------------------------ |
| 👀 Síntoma    | ¿Qué veo?                      |
| ⚙️ Causa      | ¿Qué lo provoca?               |
| 🌳 Causa raíz | ¿Qué hace que siga ocurriendo? |

---

## 👨‍💻 Ejemplo en programación

Problema:

```text
La consulta PostgreSQL es lenta.
```

### 👀 Síntoma

```text
Consulta lenta.
```

### ⚙️ Causa

```text
La tabla tiene millones de registros.
```

### 🌳 Causa raíz

```text
No existe un proceso para eliminar duplicados
ni archivar datos antiguos.
```

---

## 🎯 Regla

🔴 Trabajar el síntoma:

```text
Optimizar una consulta.
```

🟢 Trabajar la causa raíz:

```text
Mejorar el proceso de calidad de datos.
```

---

# 🔍 Técnica 1: Los 5 porqués

Objetivo:

> Seguir preguntando "¿Por qué?" hasta llegar al origen.

---

## Ejemplo Data Engineer

Problema:

```text
El pipeline demora demasiado.
```

### 1️⃣ ¿Por qué?

```text
Porque PostgreSQL está lento.
```

### 2️⃣ ¿Por qué?

```text
Porque la tabla tiene demasiados registros.
```

### 3️⃣ ¿Por qué?

```text
Porque hay muchos duplicados.
```

### 4️⃣ ¿Por qué?

```text
Porque el proceso ETL no valida duplicados.
```

### 5️⃣ ¿Por qué?

```text
Porque nunca se definieron reglas de calidad de datos.
```

🌳 Causa raíz:

```text
Falta de reglas de calidad de datos.
```

---

## ⚠️ Importante

No siempre son exactamente cinco.

La pregunta correcta es:

> **¿Puedo seguir profundizando o ya llegué al fondo?**

---

## ❌ Error común

No bajar de nivel:

```text
¿Por qué falla?

Porque está mal.

¿Por qué está mal?

Porque falla.
```

Eso es repetir ideas.

Cada respuesta debe aportar algo nuevo.

---

# 👀 Técnica 2: Las tres ventanas

Los 5 porqués profundizan.

Las tres ventanas amplían la visión.

Pregunta:

```text
¿Estoy mirando el problema desde todos los ángulos?
```

---

## 👤 Usuario

¿Qué experimenta?

Ejemplo:

```text
El analista espera mucho tiempo para obtener datos.
```

---

## ⚙️ Proceso

¿Dónde se rompe?

Ejemplo:

```text
La carga de datos no elimina duplicados.
```

---

## 🏢 Organización

¿Qué permite que ocurra?

Ejemplo:

```text
No existen reglas ni responsables de calidad de datos.
```

---

# 👨‍💻 Ejemplo completo

Problema:

```text
Los dashboards se actualizan tarde.
```

### 👤 Usuario

```text
Los analistas esperan horas.
```

### ⚙️ Proceso

```text
La transformación de datos es manual.
```

### 🏢 Organización

```text
Nunca se automatizó el proceso.
```

---

# 🛠 Método completo

```text
Problema
    ↓
5 Porqués
    ↓
Causa raíz
    ↓
Tres ventanas
    ↓
Nueva información
    ↓
Problema reformulado
    ↓
IA
```

---

# 🤖 Cómo cambia el prompt

## ❌ Mal prompt (síntoma)

```text
Mi consulta SQL es lenta.
¿Cómo la optimizo?
```

La IA responderá:

```text
Crea índices.
Usa EXPLAIN.
Particiona tablas.
```

Consejos generales.

---

## ✅ Buen prompt (causa raíz)

```text
Soy Data Engineer.

Mi consulta PostgreSQL es lenta.

Después de aplicar los 5 porqués encontré que
el problema principal no es SQL sino que el
pipeline no elimina duplicados y las tablas
crecen innecesariamente.

Desde las tres ventanas encontré:

Usuario:
Los analistas esperan mucho.

Proceso:
No existe validación de duplicados.

Organización:
No hay reglas de calidad de datos.

Ayúdame a diseñar un proceso automático de
validación antes de cargar datos.
```

Ahora la IA trabajará sobre el problema real.

---

# 🧠 Ejemplo rápido para tu proyecto de personas desaparecidas

Problema inicial:

```text
Las consultas PostgreSQL son lentas.
```

### 5 porqués

```text
Consulta lenta
↓
Muchos registros
↓
Duplicados
↓
CSV mal preparado
↓
No existe validación automática
```

🌳 Causa raíz:

```text
Falta de calidad de datos antes de importar.
```

---

### Tres ventanas

👤 Usuario:

```text
El analista demora en obtener información.
```

⚙️ Proceso:

```text
El CSV entra sin validaciones.
```

🏢 Organización:

```text
No existe un flujo estándar de limpieza.
```

---

# 🎯 Resumen

Cuando un problema aparece:

```text
1. ¿Qué veo?
   → Síntoma.

2. ¿Qué lo provoca?
   → Causa.

3. ¿Qué hace que siga ocurriendo?
   → Causa raíz.
```

Y antes de preguntarle a la IA:

```text
5 Porqués
      +
Tres Ventanas
      ↓
Problema reformulado
      ↓
IA
      ↓
Mejores respuestas
```

💡 Frase para recordar:

> **La IA puede ayudarte a resolver problemas, pero primero tú debes descubrir cuál es el problema real.**

## 🧠 Organizar la información antes de usar IA

## 💡 Idea principal — Feynman

> **La IA no arregla automáticamente el desorden de tus ideas. Si le das información desordenada, puede devolverte una respuesta bien redactada, pero igualmente desordenada.**

Antes de pedir ayuda:

```text
📄 Información cruda
      ↓
🗂️ Categorizar
      ↓
🔄 Secuenciar
      ↓
🎯 Priorizar
      ↓
🤖 IA
      ↓
🚀 Resultado útil
```

---

# 🗂️ 1. Categorizar

### ¿Qué significa?

> **Agrupar cosas que tienen algo en común y ponerles una etiqueta útil.**

No basta con crear grupos; el nombre debe ayudarte a entender el contenido.

### ❌ Mal

```text
- Varios
- Otros
- General
```

### ✅ Bien

```text
📦 Producto
🤝 Posventa
💬 Comunicación
```

### 💡 ¿Qué conseguimos?

Las categorías permiten **ver patrones** que antes estaban escondidos.

---

## 👨‍💻 Ejemplo en Data Engineering

Tienes 10 problemas:

```text
- CSV con duplicados
- PostgreSQL lento
- Columnas incorrectas
- API falla
- Datos nulos
- Consulta sin índice
- Python tarda mucho
```

Puedes agrupar:

### 📊 Datos

* CSV con duplicados.
* Columnas incorrectas.
* Datos nulos.

### 🗄️ Base de datos

* PostgreSQL lento.
* Consulta sin índice.

### 🐍 Código

* Python tarda mucho.

### 🌐 Integraciones

* API falla.

Ahora el problema ya tiene estructura.

---

# 🔄 2. Secuenciar

Categorizar responde:

> **¿Qué cosas tengo?**

Secuenciar responde:

> **¿En qué orden deben hacerse?**

La clave no es solamente el tiempo, sino las **dependencias**.

---

## 🔗 Regla principal

> **Primero resuelve lo que desbloquea al resto.**

Ejemplo:

```text
Definir producto
      ↓
Diseñar programa
      ↓
Lanzar capacitación
```

No puedes lanzar una capacitación si todavía no sabes qué programa vas a ofrecer.

---

## 👨‍💻 Ejemplo de un proyecto

Quieres crear un pipeline:

```text
CSV
 ↓
Limpieza
 ↓
Transformación
 ↓
PostgreSQL
 ↓
Dashboard
```

No tendría sentido comenzar creando el dashboard si todavía no sabes si los datos están limpios.

### ❌ Orden por "lo que me provoca hacer"

```text
Dashboard
→ PostgreSQL
→ CSV
→ Limpieza
```

### ✅ Orden por dependencia

```text
CSV
 ↓
Limpieza
 ↓
Transformación
 ↓
PostgreSQL
 ↓
Dashboard
```

---

# 🎯 3. Priorizar

Aquí aparece una pregunta diferente:

> **¿Qué debería hacer primero y con qué criterio?**

No deberías priorizar simplemente por:

* 🚨 quién presiona más;
* ⏰ qué parece más urgente;
* 🟢 qué es más fácil.

Primero define el **criterio**.

### Ejemplo

```text
Priorizar por:

🎯 Impacto
+
🛠️ Facilidad de implementación
```

Entonces puedes comparar las tareas usando esos criterios.

---

# 🧩 Ejemplo completo

Supongamos que tienes estos problemas en un proyecto de datos:

```text
- CSV tiene duplicados
- Dashboard tiene mal diseño
- PostgreSQL está lento
- No existen validaciones
- API es difícil de mantener
- Usuarios quieren nuevos gráficos
```

## 1️⃣ Categorizar

```text
📊 Calidad de datos
- Duplicados
- Falta de validaciones

🗄️ Base de datos
- PostgreSQL lento

📈 Producto
- Nuevos gráficos
- Diseño del dashboard

🌐 Código
- API difícil de mantener
```

---

## 2️⃣ Secuenciar

Podríamos encontrar esta dependencia:

```text
Calidad de datos
      ↓
Base de datos
      ↓
Dashboard
```

Porque no tiene mucho sentido mejorar el dashboard si los datos que consume todavía son incorrectos.

---

## 3️⃣ Priorizar

Definimos:

> **Priorizar por impacto y facilidad de implementación.**

Ahora ya podemos pedirle a la IA que nos ayude a analizar las tareas **bajo ese criterio**, en lugar de pedirle simplemente:

```text
"¿Qué debería hacer primero?"
```

---

# 🤖 Cómo pedirlo a la IA

### ❌ Prompt débil

```text
Tengo estos problemas:

- PostgreSQL lento
- CSV con duplicados
- Dashboard feo
- API complicada

¿Qué hago?
```

La IA tendrá que inventar el criterio.

---

### ✅ Prompt estructurado

```text
Tengo un proyecto de Data Engineering.

CATEGORÍAS:

Calidad de datos:
- CSV con duplicados
- No existen validaciones

Base de datos:
- PostgreSQL lento

Producto:
- Dashboard necesita mejoras

DEPENDENCIAS:

CSV
→ Validación
→ PostgreSQL
→ Dashboard

CRITERIO:

Quiero priorizar por:
1. Impacto
2. Facilidad de implementación

Analiza las tareas utilizando únicamente estos
criterios y explica qué información adicional
necesitarías para hacerlo correctamente.
```

🔥 Aquí la IA ya tiene:

* **qué información analizar**;
* **cómo está organizada**;
* **qué depende de qué**;
* **con qué criterio analizarla**.

---

# 🧠 Diferencia entre los 3 conceptos

| Concepto        | Pregunta                        | Resultado |
| --------------- | ------------------------------- | --------- |
| 🗂️ Categorizar | ¿Qué cosas se parecen?          | Grupos    |
| 🔄 Secuenciar   | ¿Qué depende de qué?            | Orden     |
| 🎯 Priorizar    | ¿Qué criterio uso para decidir? | Enfoque   |

---

# 🔥 Conexión con lo anterior

Estas técnicas se van acumulando:

```text
1. 🧩 Descomponer
   ↓
   Listar → Agrupar → Conectar → Priorizar

2. 🌳 Encontrar causa raíz
   ↓
   5 Porqués + Tres ventanas

3. 🗂️ Estructurar información
   ↓
   Categorizar → Secuenciar → Priorizar

4. 🤖 Finalmente
   ↓
   Crear el prompt
```

### 🎯 La idea que debes quedarte

> **Primero pienso → después organizo → finalmente le pido a la IA que me ayude.**

Y para programación/Data Engineering:

> **No le entregues a la IA una lista de problemas. Entrégale categorías, dependencias y un criterio.**

