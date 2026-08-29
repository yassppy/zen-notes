# 01_fundamentos

## 📊 Power BI y Fundamentos de Data Analytics

## 🚀 ¿Por que crearon Power BI?

La competencia ya dominaba el mercado de BI, por eso Microsoft unificó herramientas que antes estaban separadas en Excel. Creando **Power BI** para facilitar el análisis de datos y la creación de dashboards interactivos.

Hoy Power BI incluso incorpora IA 🤖 (Copilot) para consultar datos usando lenguaje natural.

---

## 💡 Flujo del Análisis de Datos

El análisis de datos NO es solo hacer gráficos.

El flujo correcto es:

```text
🧠 Pensar → 🧹 Preparar → 🏗️ Modelar → 📏 Medir → 📖 Contar
```

| Etapa       | ¿Qué se hace?                   |
| ----------- | ------------------------------- |
| 🧠 Pensar   | Definir preguntas del negocio   |
| 🧹 Preparar | Limpiar y transformar datos     |
| 🏗️ Modelar | Relacionar tablas correctamente |
| 📏 Medir    | Crear KPIs y métricas con DAX   |
| 📖 Contar   | Mostrar insights con dashboards |

---

## 🧠 1. Pensar como Data Analyst

Vamos a estar preguntando que esta pasando con la data y que acciones podemos tomar.

### ❌ Pregunta Débil

> “Quiero ver las ventas”

👉 Muy general.

---

### ⚡ Pregunta Fuerte

> “¿Qué región y categoría explican el crecimiento de ventas?”

👉 Tiene dirección y contexto.

---

### 🎯 Pregunta Accionable

> “¿Dónde invertir para aumentar utilidad sin perder margen?”

👉 Ayuda a tomar decisiones reales.

---

### 🔍 Las 3 Preguntas Clave de la Analítica

| Pregunta                  | Objetivo                     |
| ------------------------- | ---------------------------- |
| 📌 ¿Qué está pasando?     | Detectar cambios o problemas |
| 🔎 ¿Por qué está pasando? | Encontrar la causa           |
| 🚀 ¿Qué debemos hacer?    | Proponer acciones            |

---

## 🧠 Fórmula de un Insight Profesional

Un insight útil tiene:

```text
📊 Dato + 🧠 Contexto + 🚀 Acción
```

la idea es explicar una causa y proponer una acción que es la recomendación.

### 📝 Plantilla

> “Observamos [cambio], principalmente en [segmento], porque [causa]. Recomendamos [acción] para lograr [resultado].”

---

### Ejemplos:

Caso 1: Empresa de Delivery: 
- *Insight:* "Observamos una **caída del 12% en la tasa de recompra**, principalmente en la **Zona Norte**, porque **los tiempos de entrega excedieron los 45 minutos (evidencia)**. Recomendamos **redistribuir la flota de repartidores hacia los nodos críticos de esa zona** para **recuperar el nivel de servicio habitual**.

---

## 📊 Tipos de Dashboards

| Tipo de Dashboard  | 👤 Usuarios               | 🎯 Objetivo                       | 📌 KPIs / Características                               |
| ------------------ | ------------------------- | --------------------------------- | ------------------------------------------------------- |
| 🏢 **Estratégico** | Directivos y gerencia     | Ver el estado general del negocio | ROI, Ventas, Utilidad, Margen                           |
| 🛠️ **Táctico**    | Gerentes y líderes        | Monitorear objetivos del área     | Cuotas, Inventario, Rendimiento regional                |
| ⚙️ **Operativo**   | Supervisores y operadores | Control diario y tiempo real      | Tickets, Inventario, Despachos, Alertas                 |
| 🔬 **Analítico**   | Analistas y equipos BI    | Explorar patrones y tendencias    | Drill-down, Slicers, Segmentación, Exploración profunda |


---

## ⚙️ 3. Desarrollo Técnico en Power BI

```text
🧹 Power Query → 🏗️ Modelado → 📏 DAX → 🎨 Dashboard → ☁️ Service
```

---

### 🧹 Fase 1: Power Query (ETL)

Aquí se limpian los datos.

## ✅ Tareas principales

* Corregir tipos de datos 🔢
* Eliminar nulos ❌
* Quitar duplicados 🧹
* Crear columnas útiles 🏷️
* Estandarizar nombres ✍️
* Validar calidad ✔️

---

### 🏗️ Fase 2: Modelado

Se organizan las tablas.

#### 📌 Tipos de tablas

| Tipo               | Función              |
| ------------------ | -------------------- |
| 📦 Tabla Hechos    | Guarda transacciones |
| 🧾 Tabla Dimensión | Describe información |

---

#### ✅ Ejemplo

| Hecho  | Dimensiones                |
| ------ | -------------------------- |
| Ventas | Clientes, Productos, Fecha |

---

#### ⚠️ Regla de Oro

❌ Evitar relaciones Muchos a Muchos (`*:*`)

Problemas:

* Duplica datos
* Rompe cálculos
* Reduce rendimiento

✅ Usar:

```text
⭐ Modelo Estrella (Star Schema)
```

---

### 📏 Fase 3: DAX

DAX sirve para crear métricas y KPIs.

#### 📌 Ejemplos

* Ventas Totales
* Margen %
* Ticket Promedio
* Crecimiento Mensual

---

### 🎨 Fase 4: Dashboard (UI/UX)

Un buen dashboard debe ser fácil de leer

| Zona        | Contenido           |
| ----------- | ------------------- |
| 🔝 Superior | Filtros             |
| 📊 Medio    | KPIs                |
| 📈 Centro   | Tendencias          |
| 📋 Inferior | Detalles e insights |

---

## 🧠 Ideas Clave para Recordar

```text
Un Data Analyst convierte datos en decisiones
```