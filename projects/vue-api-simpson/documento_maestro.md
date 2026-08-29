# documento_maestro

# DOCUMENTO MAESTRO
## Vue.js: Aplicación de The Simpsons API

**Frontend completo, sin login, sin backend propio y publicado en GitHub Pages**

Documento técnico base para construir el curso y la aplicación por fases, usando **Bun** como gestor de paquetes/runtime y **DaisyUI (sobre Tailwind CSS)** como sistema de diseño.

---

## 1. Control del documento

| Campo                 | Valor                                                                               |
| --------------------- | ----------------------------------------------------------------------------------- |
| Nombre                | Documento maestro de desarrollo — Vue.js con The Simpsons API                       |
| Versión               | 1.0                                                                                 |
| Estado                | Aprobado como base de implementación                                                |
| Responsable funcional | Migue                                                                               |
| Objetivo              | Guiar la creación del proyecto, las clases del curso, las pruebas y la publicación. |

---

## 2. Resumen ejecutivo

Se desarrollará una aplicación web SPA con **Vue.js 3 y Vite**, gestionada con **Bun**. La página principal presentará el curso y dará acceso al único módulo del proyecto: **The Simpsons**. El módulo tendrá listado, filtro, paginación, detalle, estado de carga y manejo de errores. No habrá autenticación, registro, roles, base de datos ni backend propio.

La primera versión de todas las vistas será deliberadamente sencilla: componentes y clases básicas de **DaisyUI**, sin animaciones complejas ni personalizaciones visuales extensas. La última fase estará dedicada a mejorar la apariencia, experiencia responsive y consistencia visual, sin cambiar la lógica ya validada.

> **Principio de implementación:** primero se construye la funcionalidad completa y verificable del módulo Simpsons. El diseño visual avanzado se realiza únicamente después de que el módulo funcione correctamente de punta a punta.

---

## 3. Objetivo general

Construir una aplicación Vue.js modular que consuma **The Simpsons API**, aplique una arquitectura frontend ordenada y permita enseñar de forma progresiva componentes, rutas, servicios, solicitudes HTTP, filtrado, paginación, vista de detalle, manejo de estados y despliegue en GitHub Pages.

---

## 4. Objetivos específicos

- Crear una página principal con información del curso y acceso al proyecto Simpsons.
- Consumir datos públicos mediante Axios desde un servicio independiente (`simpsonsService.js`).
- Separar vistas, componentes, servicios, helpers, router y estilos.
- Implementar un filtro de búsqueda acorde con las capacidades reales de la API (no hay endpoint de búsqueda oficial: se filtra la página cargada).
- Implementar la paginación nativa que entrega la API (`page`).
- Construir una vista de detalle mediante ruta dinámica (`/simpsons/:id`).
- Manejar carga, errores, resultados vacíos y navegación no encontrada.
- Compilar el proyecto con Vite (usando Bun) y publicarlo en GitHub Pages.
- Cerrar el curso con una fase final de mejora visual y responsive con DaisyUI.

---

## 5. Alcance funcional

### 5.1 Incluido

- Aplicación SPA en un solo repositorio.
- Home con presentación del curso y una tarjeta de acceso al proyecto Simpsons.
- Módulo The Simpsons: listado, filtro, paginación y detalle de personajes.
- **Tailwind CSS + DaisyUI** para la interfaz, instalados y gestionados con **Bun**.
- Axios para las solicitudes HTTP.
- SweetAlert2 únicamente cuando aporte claridad en errores relevantes o avisos puntuales (opcional).
- Vue Router con historial hash (`createWebHashHistory`) para compatibilidad directa con GitHub Pages.
- Publicación automática o manual de la carpeta compilada `dist`.

### 5.2 No incluido (funcionalidad que NO se va a implementar)

- **Bootstrap** — se reemplaza completamente por DaisyUI/Tailwind; no se debe instalar ni mezclar con las clases nuevas.
- **npm/yarn como gestor principal** — se reemplaza por **Bun** (`bun install`, `bun run dev`, `bunx`).
- Login, registro, recuperación de contraseña o autenticación.
- Roles, permisos o panel administrativo.
- Backend propio, NestJS, Laravel, Node.js en producción o base de datos.
- CRUD de creación, edición o eliminación de datos (la API es de solo lectura).
- Pasarela de pagos, carrito, favoritos persistentes o cuentas de usuario.
- Pinia u otra librería de estado global en la primera versión, porque el estado no necesita compartirse fuera del módulo Simpsons.
- Diseño visual avanzado durante las primeras fases (se deja para la fase final).
- Búsqueda global remota: la API no expone un parámetro oficial de búsqueda por texto, así que no se simula un endpoint que no existe.

---

## 6. Tecnologías y dependencias

| Tecnología | Uso | Decisión |
|---|---|---|
| **Bun** | Runtime y gestor de paquetes | Reemplaza a npm/yarn: `bun install`, `bun run dev`, `bun run build`. Más rápido para instalar dependencias y correr scripts. |
| Vue.js 3 | Componentes y Composition API | Framework principal del frontend. |
| Vite | Servidor de desarrollo y build | Generará la carpeta `dist` para GitHub Pages. Se ejecuta a través de Bun. |
| JavaScript | Lógica de la aplicación | Se mantiene la extensión `.js`; no se introduce TypeScript. |
| Vue Router | Navegación SPA | Se utilizará `createWebHashHistory` para evitar 404 al recargar. |
| Axios | Consumo de la API | Cliente común en `services/api.js`. |
| **Tailwind CSS** | Motor de utilidades CSS | Base sobre la que corre DaisyUI, vía `@tailwindcss/vite`. |
| **DaisyUI** | Componentes de interfaz | Reemplaza a Bootstrap. Se declara como plugin de Tailwind (`@plugin "daisyui";`). Interfaz básica, clara y responsive desde el inicio. |
| SweetAlert2 | Avisos puntuales | Uso opcional; no reemplaza todos los estados de error manejados con clases `alert` de DaisyUI. |
| GitHub Pages | Hosting estático | Publicación del frontend compilado. |

### Instalación base con Bun + Vite + DaisyUI

```bash
# Crear el proyecto Vue con Vite
bun create vite@latest simpsons-explorer -- --template vue
cd simpsons-explorer

# Instalar dependencias del proyecto
bun install

# Tailwind CSS + DaisyUI (Tailwind v4, sin archivo de configuración clásico)
bun add -d tailwindcss @tailwindcss/vite daisyui@latest

# Axios y Vue Router
bun add axios vue-router
```

`vite.config.js`:

```js
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [vue(), tailwindcss()],
  base: '/nombre-del-repositorio/',
})
```

`src/assets/main.css`:

```css
@import "tailwindcss";
@plugin "daisyui";
```

Comandos de trabajo diario con Bun:

```bash
bun run dev      # servidor de desarrollo
bun run build    # genera la carpeta dist
bun run preview  # revisa el build localmente
```

---

## 7. Arquitectura de navegación

La aplicación utilizará URLs con hash al publicarse en GitHub Pages, por ejemplo:

```
https://usuario.github.io/simpsons-explorer/#/simpsons/1
```

Rutas del proyecto:

```
INICIO
│
├── /simpsons
│   └── /simpsons/:id
│
└── /:pathMatch(.*)*   → 404
```

---

## 8. Estructura oficial del proyecto

```
📦src
 ┣ 📂assets
 ┃ ┗ 📜main.css
 ┣ 📂components
 ┃ ┣ 📜AppNavbar.vue
 ┃ ┣ 📜AppFooter.vue
 ┃ ┣ 📜LoadingSpinner.vue
 ┃ ┣ 📜SearchInput.vue
 ┃ ┣ 📜AppPagination.vue
 ┃ ┗ 📜EmptyResults.vue
 ┣ 📂helpers
 ┃ ┗ 📜errorHelper.js
 ┣ 📂router
 ┃ ┗ 📜index.js
 ┣ 📂services
 ┃ ┣ 📜api.js
 ┃ ┗ 📜simpsonsService.js
 ┣ 📂views
 ┃ ┣ 📜HomeView.vue
 ┃ ┣ 📜SimpsonsView.vue
 ┃ ┣ 📜SimpsonsDetailView.vue
 ┃ ┗ 📜NotFoundView.vue
 ┣ 📜App.vue
 ┗ 📜main.js
```

Nota: se elimina `ProjectCard.vue` como tarjeta genérica de "tres proyectos" porque ya no hay tres proyectos; `HomeView.vue` presenta directamente el curso y un único acceso al módulo Simpsons (puede seguir usando una tarjeta simple, pero ya no es un componente reutilizable entre módulos).

---

## 9. Responsabilidad de los archivos (significado sencillo)

| Archivo | Qué hace, en simple |
|---|---|
| `assets/main.css` | Importa Tailwind y DaisyUI; aquí van los ajustes visuales de la fase final. |
| `components/AppNavbar.vue` | La barra de navegación de arriba: enlaces a Inicio y a Simpsons. |
| `components/AppFooter.vue` | El pie de página que se repite en todas las vistas. |
| `components/LoadingSpinner.vue` | El "cargando..." que se muestra mientras se espera la respuesta de la API. |
| `components/SearchInput.vue` | El cuadro de texto para filtrar personajes por nombre. |
| `components/AppPagination.vue` | Los botones de "anterior / siguiente / número de página". |
| `components/EmptyResults.vue` | El mensaje que aparece cuando el filtro no encuentra ningún personaje. |
| `helpers/errorHelper.js` | Traduce un error técnico de Axios en un mensaje simple para el usuario. |
| `services/api.js` | La configuración única de Axios (URL base, timeout) que usa el resto de servicios. |
| `services/simpsonsService.js` | Las funciones que piden datos a The Simpsons API: listado por página y detalle por ID. |
| `router/index.js` | El mapa de rutas de la aplicación (qué URL muestra qué vista). |
| `views/HomeView.vue` | La pantalla de inicio: presenta el curso y el acceso al módulo. |
| `views/SimpsonsView.vue` | La pantalla de listado: muestra las tarjetas de personajes, el filtro y la paginación. |
| `views/SimpsonsDetailView.vue` | La pantalla de detalle: muestra la información completa de un personaje. |
| `views/NotFoundView.vue` | La pantalla que aparece si la URL no corresponde a ninguna ruta válida. |
| `App.vue` | El molde general: navbar arriba, el contenido de cada vista en el medio, footer abajo. |
| `main.js` | El punto de arranque: aquí se crea la app de Vue y se conectan el router y los estilos. |

---

## 10. Especificación de la API — The Simpsons API

- Sitio oficial: https://thesimpsonsapi.com/
- URL base: `https://thesimpsonsapi.com/api`
- No requiere autenticación ni API key.
- El recurso principal (y único, para este curso) es **characters**.
- El listado devuelve `count`, `next`, `prev`, `pages` y `results`.
- Cada página contiene exactamente **20 registros** y el tamaño de página no puede personalizarse.
- El detalle de un personaje se consulta por **ID**.
- Los registros pueden incluir: nombre, edad, género, ocupación, estado, frases, descripción y `portrait_path`.

### Cómo se consume el endpoint

```
GET https://thesimpsonsapi.com/api/characters            → página 1 (por defecto)
GET https://thesimpsonsapi.com/api/characters?page=2     → página 2
GET https://thesimpsonsapi.com/api/characters/1          → detalle del personaje con ID 1
```

`services/simpsonsService.js` debe exponer, como mínimo:

```js
// Obtiene una página del listado
getCharacters(page = 1)   // GET /characters?page=page

// Obtiene el detalle de un personaje
getCharacterById(id)      // GET /characters/{id}
```

**Estrategia de búsqueda:** la documentación pública consultada no describe un parámetro oficial de búsqueda por texto. Para mantener el módulo simple y honesto con lo que la API realmente ofrece, la primera versión filtra en el frontend los 20 registros de la página actual cargada (con `SearchInput.vue` + un `computed`). No se implementa una búsqueda global sobre todos los personajes en esta fase; queda documentado como posible mejora futura, no como funcionalidad entregada.

**Imágenes:** la API devuelve rutas relativas mediante `portrait_path`, servidas por CDN. La URL final de la imagen debe componerse y validarse durante la implementación (no fijar un prefijo sin confirmarlo primero contra la respuesta real de la API).

---

## 11. Requisitos funcionales

| ID | Requisito |
|---|---|
| RF-01 | Mostrar una página principal con información del curso. |
| RF-02 | Mostrar un acceso claro al módulo Simpsons desde el inicio. |
| RF-03 | Navegar entre vistas sin recargar completamente el navegador. |
| RF-04 | Listar personajes obtenidos desde The Simpsons API. |
| RF-05 | Permitir filtrar los personajes visibles por nombre. |
| RF-06 | Permitir avanzar y retroceder entre páginas usando `page`. |
| RF-07 | Mostrar una vista de detalle por personaje. |
| RF-08 | Mostrar un indicador mientras se consulta la API. |
| RF-09 | Mostrar un mensaje cuando el filtro no arroje resultados. |
| RF-10 | Mostrar un mensaje comprensible cuando ocurra un error de red o de API. |
| RF-11 | Permitir volver al listado desde el detalle. |
| RF-12 | Mostrar una vista 404 para rutas inválidas. |
| RF-13 | Funcionar correctamente publicada en GitHub Pages. |
| RF-14 | Mantener una interfaz responsive en móvil, tablet y escritorio. |

---

## 12. Estados mínimos de la vista

- **Estado inicial:** título, descripción corta, buscador y espacio del listado.
- **Estado cargando:** `LoadingSpinner` visible y acciones temporalmente deshabilitadas.
- **Estado correcto:** tarjetas con información de personajes y controles de paginación.
- **Estado sin resultados:** `EmptyResults` con un mensaje específico del módulo.
- **Estado de error:** alerta con clase `alert` de DaisyUI y, cuando sea relevante, SweetAlert2.
- **Estado de detalle no encontrado:** mensaje y botón para regresar al listado.

---

## 13. Criterios visuales de la primera versión (con DaisyUI)

- Navbar básica con `navbar` de DaisyUI y enlaces `RouterLink`.
- Contenedor con clases de layout de Tailwind (`container`, `mx-auto`, `p-4`) en lugar de la grilla de Bootstrap.
- Tarjetas de personajes usando el componente `card` de DaisyUI (`card`, `card-body`, `card-title`).
- Buscador con `input` + `input-bordered` de DaisyUI.
- Paginación con `join` y `btn` de DaisyUI (patrón oficial de paginación de DaisyUI).
- Detalle con una disposición simple de imagen + información, usando utilidades de Tailwind para el layout.
- Sin gradientes complejos, fondos temáticos, animaciones o efectos 3D en las fases iniciales.
- El propósito inicial es facilitar la explicación del código y verificar la funcionalidad, no lucir terminado.

---

## 14. Plan de desarrollo por fases

> **Importante:** todas las fases giran únicamente alrededor de **The Simpsons API**. No hay fases para otros módulos.

**Fase 1 — Base del proyecto**
- Objetivo: crear la aplicación Vue con Vite (vía Bun) y confirmar que se ejecuta correctamente.
- Archivos principales: `package.json`, `src/main.js`, `src/App.vue`.
- Actividades: crear el proyecto con `bun create vite`; instalar dependencias con `bun install`; ejecutar el servidor con `bun run dev`; eliminar el contenido de demostración que no se usará; verificar la estructura inicial.
- Resultado esperado: proyecto limpio ejecutándose sin errores.

**Fase 2 — Tailwind, DaisyUI, Router y Axios**
- Objetivo: configurar Tailwind CSS, DaisyUI, Vue Router y Axios.
- Archivos principales: `vite.config.js`, `src/assets/main.css`, `src/main.js`, `src/router/index.js`.
- Actividades: instalar dependencias con Bun; configurar `@tailwindcss/vite`; declarar `@plugin "daisyui";` en `main.css`; registrar el router; mantener SweetAlert2 disponible sin usarlo todavía de forma general.
- Resultado esperado: aplicación preparada para rutas, solicitudes HTTP y componentes DaisyUI.

**Fase 3 — Arquitectura de carpetas**
- Objetivo: construir la arquitectura definida en este documento antes de desarrollar funcionalidades.
- Archivos principales: `src/components/*`, `src/helpers/*`, `src/services/*`, `src/views/*`.
- Actividades: crear todas las carpetas aprobadas; crear archivos vacíos o con plantilla mínima; confirmar nombres consistentes.
- Resultado esperado: estructura completa y lista para implementación.

**Fase 4 — Navegación compartida**
- Objetivo: crear las rutas y la estructura compartida de todas las pantallas.
- Archivos principales: `src/router/index.js`, `src/App.vue`, `src/components/AppNavbar.vue`, `src/components/AppFooter.vue`, `src/views/NotFoundView.vue`.
- Actividades: definir las rutas `/simpsons` y `/simpsons/:id` con `createWebHashHistory`; crear `AppNavbar` con enlaces a Inicio y Simpsons; crear `AppFooter`; incluir `router-view` dentro de `App.vue`; crear una vista 404 sencilla.
- Resultado esperado: navegación funcional entre vistas vacías o temporales.

**Fase 5 — Página de inicio**
- Objetivo: construir una `HomeView` simple que presente el curso y el acceso al módulo Simpsons.
- Archivos principales: `src/views/HomeView.vue`.
- Actividades: crear un encabezado sencillo con título y descripción; mostrar un bloque o tarjeta DaisyUI con el acceso al módulo; evitar personalizaciones visuales avanzadas.
- Resultado esperado: inicio claro y funcional con acceso al proyecto Simpsons.

**Fase 6 — Elementos compartidos**
- Objetivo: centralizar solicitudes y preparar elementos reutilizables antes de consumir la API.
- Archivos principales: `src/services/api.js`, `src/helpers/errorHelper.js`, `src/components/LoadingSpinner.vue`, `src/components/SearchInput.vue`, `src/components/AppPagination.vue`, `src/components/EmptyResults.vue`.
- Actividades: crear la instancia Axios con timeout; crear función para obtener mensajes de error; crear spinner con clases de DaisyUI; crear input de búsqueda reutilizable; crear paginación reutilizable; crear mensaje de resultados vacíos; probar cada componente con datos temporales.
- Resultado esperado: componentes compartidos listos para usarse en el módulo Simpsons.

**Fase 7 — Listado de personajes**
- Objetivo: consumir la API y mostrar personajes con una vista básica.
- Archivos principales: `src/services/simpsonsService.js`, `src/views/SimpsonsView.vue`.
- Actividades: crear la función para obtener personajes por página; guardar `results`, `count`, `pages`, `next` y `prev`; mostrar tarjetas básicas con nombre, ocupación y estado; construir la URL de retrato cuando se confirme el prefijo oficial; conectar `AppPagination` con el parámetro `page`; mostrar `LoadingSpinner` durante cada cambio de página.
- Resultado esperado: listado de personajes paginado mediante la información entregada por la API.

**Fase 8 — Filtro y detalle**
- Objetivo: completar el módulo con filtro local y ruta dinámica de personaje.
- Archivos principales: `src/views/SimpsonsView.vue`, `src/views/SimpsonsDetailView.vue`, `src/router/index.js`, `src/services/simpsonsService.js`.
- Actividades: filtrar por nombre los resultados de la página actual; restablecer el filtro al cambiar de página; crear la función de detalle por ID; mostrar descripción, ocupación, estado, frases y datos disponibles; agregar botón "Volver"; controlar personaje inexistente y errores de red.
- Resultado esperado: módulo Simpsons completo, simple y funcional.

**Fase 9 — Consistencia de experiencia de usuario**
- Objetivo: revisar el módulo y aplicar un comportamiento uniforme ante carga, error y listas vacías.
- Archivos principales: `src/helpers/errorHelper.js`, `src/components/LoadingSpinner.vue`, `src/components/EmptyResults.vue`, `src/views/*.vue`.
- Actividades: evitar duplicación de mensajes; deshabilitar controles durante solicitudes; diferenciar error de red, timeout, 404 y respuesta inválida; usar `alert` de DaisyUI para errores persistentes; usar SweetAlert2 únicamente para avisos puntuales; limpiar estados anteriores al iniciar una nueva solicitud.
- Resultado esperado: comportamiento consistente ante carga, error y listas vacías.

**Fase 10 — Revisión general**
- Objetivo: revisar la aplicación completa antes de compilarla.
- Archivos principales: `src/**/*`.
- Actividades: recorrer todos los enlaces del navbar; probar filtros vacíos, válidos e inválidos; probar primera y última página; abrir detalles y regresar al listado; eliminar código temporal y `console.log` innecesarios; revisar nombres de funciones y comentarios; confirmar que no existen imports sin utilizar.
- Resultado esperado: aplicación funcional completa con diseño básico.

**Fase 11 — Build y publicación**
- Objetivo: generar el build de producción con Bun y publicar la SPA desde un único repositorio.
- Archivos principales: `vite.config.js`, `package.json`, `.github/workflows/deploy.yml`, `README.md`.
- Actividades: configurar `base` con el nombre del repositorio; ejecutar `bun run build`; probar localmente la carpeta `dist` con `bun run preview`; configurar GitHub Pages con GitHub Actions (usando Bun en el workflow) o una rama de despliegue; confirmar rutas hash y carga de recursos; documentar instalación, ejecución y URL pública.
- Resultado esperado: aplicación accesible públicamente desde GitHub Pages.

**Fase 12 — Mejora visual final**
- Objetivo: transformar la interfaz funcional básica en una experiencia visual más profesional con DaisyUI, sin alterar la lógica.
- Archivos principales: `src/assets/main.css`, `src/components/*.vue`, `src/views/*.vue`.
- Actividades: definir identidad visual común (tema de DaisyUI); mejorar hero, tarjetas, sombras, espaciado y jerarquía tipográfica; aplicar un tema de DaisyUI (`data-theme`) coherente; mejorar placeholders o transiciones simples si aportan claridad; optimizar responsive en móvil, tablet y escritorio; revisar accesibilidad básica (contraste, textos alternativos, botones); volver a compilar, publicar y realizar una prueba final.
- Resultado esperado: versión final visualmente mejorada, responsive y publicada.

---

## 15. Criterios de aceptación final

- ☐ La página principal explica el proyecto y muestra el acceso funcional al módulo Simpsons.
- ☐ El navbar permite ir entre Inicio y Simpsons.
- ☐ El listado carga datos reales desde The Simpsons API.
- ☐ El módulo dispone de filtro por nombre y paginación nativa (`page`).
- ☐ El módulo dispone de una vista de detalle.
- ☐ Las pantallas controlan carga, error y resultados vacíos.
- ☐ No existe login, registro, backend ni base de datos.
- ☐ La aplicación se adapta a pantallas móviles y de escritorio.
- ☐ `bun run build` finaliza correctamente.
- ☐ La URL de GitHub Pages carga sin errores de rutas ni archivos estáticos.
- ☐ La fase visual final no rompe el filtro, la paginación ni la navegación.

---

## 16. Riesgos y decisiones técnicas

| Riesgo | Impacto | Tratamiento |
|---|---|---|
| Cambio en The Simpsons API | Endpoints o campos pueden cambiar sin control del curso. | Centralizar URL y transformación de datos en `simpsonsService.js`; revisar la documentación antes de grabar cada clase. |
| CORS o caída temporal de la API | La aplicación no puede completar una solicitud. | Mostrar error amigable y verificar el estado del servicio antes de asumir un fallo del código. |
| Búsqueda limitada a la página actual | No existe endpoint oficial de búsqueda por texto. | Filtrar la página cargada y explicar la limitación en la interfaz; documentar la búsqueda global como posible extensión futura, no como entrega. |
| GitHub Pages y rutas | Las rutas "limpias" pueden devolver 404 al recargar. | Usar `createWebHashHistory`. |
| Migración de Bootstrap a DaisyUI | Riesgo de mezclar clases de ambos sistemas si se copian ejemplos antiguos. | No instalar Bootstrap en este proyecto; usar exclusivamente clases de Tailwind/DaisyUI. |
| Exceso de diseño temprano | Dificulta explicar y depurar el curso. | Mantener DaisyUI con clases básicas hasta la fase 12. |

---

## 17. Convenciones de desarrollo

- Componentes y vistas en PascalCase: `SimpsonsView.vue`, `AppPagination.vue`.
- Servicios y helpers en camelCase: `simpsonsService.js`, `errorHelper.js`.
- Funciones descriptivas: `getCharacters`, `getCharacterById`.
- Estados booleanos con prefijo `is`: `isLoading`, `isSearching`.
- No realizar solicitudes HTTP directamente desde componentes reutilizables.
- No duplicar la URL base en varias vistas; centralizarla en `services/api.js`.
- Los comentarios deben explicar intención o decisión, no repetir literalmente el código.
- Evitar componentes excesivamente pequeños si no serán reutilizados.
- No incluir información sensible en variables de entorno; esta API no requiere claves.
- Mantener las clases de DaisyUI visibles y comprensibles para estudiantes (evitar abstraer todo en componentes CSS personalizados desde el inicio).

---

## 18. Estrategia de publicación

- Repositorio único con todo el código fuente.
- Rama `main` como fuente de desarrollo.
- GitHub Actions ejecuta `bun install` y `bun run build` (usando una acción que instale Bun, por ejemplo `oven-sh/setup-bun`).
- El artefacto publicado será la carpeta `dist`.
- Vite debe usar `base` igual al nombre del repositorio.
- Vue Router utilizará historial hash.
- Cada actualización confirmada en `main` generará un nuevo despliegue.
- El README incluirá descripción, tecnologías (Vue, Vite, Bun, DaisyUI, Axios), instalación, comandos y enlace público.

---

## 19. Fuentes oficiales consultadas

Fecha de consulta: 25 de agosto de 2026. Las APIs públicas y las herramientas de frontend pueden cambiar; antes de grabar el módulo se debe repetir una verificación breve de endpoints, políticas de la API y sintaxis de instalación de DaisyUI/Bun.

| Fuente | URL | Uso en el documento |
|---|---|---|
| The Simpsons API - Documentación | https://thesimpsonsapi.com/ | URL base, recursos, detalle, campos, paginación fija e imágenes por CDN. |
| The Simpsons API - Endpoint raíz | https://thesimpsonsapi.com/api | Ruta de `characters`. |
| DaisyUI - Instalación | https://daisyui.com/docs/install/ | Sintaxis de instalación como plugin de Tailwind CSS v4. |
| Bun - Documentación | https://bun.sh/docs | Comandos de instalación y ejecución de scripts. |

---

## 20. Aprobación de alcance

> **Alcance aprobado:** una sola aplicación Vue.js, una sola publicación en GitHub Pages, **un único módulo de API pública (The Simpsons)**, sin backend, gestionada con **Bun** y con diseño **DaisyUI** básico hasta la fase final de mejora visual.

FIN DEL DOCUMENTO MAESTRO