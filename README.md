# Lex Portfolio

> Portfolio personal de **Moisés Acevedo** — Arquitecto de Sistemas IA, Operaciones y Automatización.
> Fundador de [Industrial Nodes](https://industrialnodes.com), la plataforma que convierte lenguaje natural en sistemas n8n de producción.

**→ [lex.industrialnodes.com](https://lex.industrialnodes.com)**

---

## De qué va

Construyo sistemas que sostienen operaciones reales: agentes de IA, automatización end-to-end, Business Intelligence y documentación de procesos. Más de 7 años haciéndolo para empresas de Estados Unidos, Latinoamérica y Europa.

Este repositorio contiene el sitio donde muestro ese trabajo con números, no con adjetivos.

El sitio es una single-page application estática de once secciones, sin build step y sin dependencias.

| | |
|---|---|
| **140 leads/hora** | Pico sostenido por un agente de WhatsApp en su primer día en producción |
| **7% → menos del 2%** | Tasa de error del mismo sistema, tras calibrarlo en producción |
| **$100k** | Generados el primer año de una agencia que ayudé a construir desde cero |
| **4 países** | Operando en simultáneo con sistemas de BI sincronizados |

### Qué vas a encontrar en el sitio

- **Industrial Nodes** — mi plataforma SaaS, facturando y con clientes de pago
- **Casos reales** con métricas verificables, incluidos los errores y cómo los corregí
- **Lector Lex** y **Player's Stats** — los otros dos productos que estoy construyendo
- **Publicaciones en medios** — Yahoo Finance, AP News, Bloomberg, Business Insider y 196 más
- **Contacto** con agenda embebida, por si querés hablar

---

# Cómo está hecho

## Por qué está construido así

Sin framework, sin bundler, sin dependencias de npm. **Un solo `index.html` con el CSS y el JS embebidos.**

No es minimalismo por estética, es la misma tesis que aplico en los sistemas que construyo para clientes: cada dependencia es una superficie que se puede romper sola. Un portfolio que depende de un build pipeline es un portfolio que un día deja de compilar por una versión menor de una librería que nadie recuerda haber instalado.

Lo que se gana en concreto:

- **Cero mantenimiento.** No hay `npm audit` que atender ni lockfile que actualizar.
- **Sin paso de despliegue.** Un `git push` publica. No hay CI que pueda fallar.
- **Portátil.** El archivo se abre en cualquier navegador, sin servidor, sin internet salvo por las tipografías.
- **Rápido por construcción**, no por optimización posterior: no hay JavaScript de terceros que bloquee el render, salvo el widget de agenda, que carga diferido.

Las únicas dos dependencias externas son deliberadas y aisladas: la hoja de tipografías de Google Fonts y el widget de Calendly. Si cualquiera de las dos cae, el sitio sigue funcionando y legible.

---

## Stack

| Capa | Elección | Nota |
|---|---|---|
| Markup | HTML5 semántico | Secciones con `id` para navegación por ancla |
| Estilos | CSS3 puro, embebido | Custom properties como sistema de tokens |
| Interacción | JavaScript vanilla, embebido | Scroll suave, revelados, año dinámico |
| Tipografías | Google Fonts | Cormorant Garamond · Syne · DM Mono |
| Agenda | Calendly inline widget | Único script de terceros |
| Hosting | GitHub Pages | Rama principal, carpeta raíz |

### Sistema de diseño

Los tokens viven en `:root`, así que el tema entero se cambia desde un solo bloque:

```css
--bg:     #0a0a08   /* fondo base            */
--gold:   #c9a84c   /* acento principal      */
--cream:  #f0e8d5   /* texto                 */
--accent: #4a7c59   /* acento secundario     */
```

**Tipografía por rol, no por gusto:** Cormorant Garamond para titulares (voz editorial), Syne para acentos estructurales, DM Mono para cifras, etiquetas técnicas y todo lo que deba leerse como dato.

---

## Estructura

Todo vive en `index.html`. Las secciones, en orden de scroll:

| # | `id` | Contenido |
|---|---|---|
| — | `hero` | Posicionamiento y CTA principal |
| 1 | `propuesta` | Propuesta de valor |
| 2 | `servicios` | Servicios |
| 3 | `producto` | **Industrial Nodes** — plataforma SaaS propia |
| 4 | `proyectos` | Lector Lex · Player's Stats |
| 5 | `caso` | Casos validados con métricas |
| 6 | `medios` | Publicaciones en medios internacionales |
| 7 | `dealers` | Vertical automotriz |
| 8 | `ventajas` | Ventajas competitivas |
| 9 | `herramientas` | Stack técnico |
| 10 | `cliente` | Perfil de cliente ideal |
| 11 | `contacto` | Contacto y agenda |

---

## Correr localmente

No requiere compilación.

**Abrir el archivo directo** — sirve para revisar contenido:

```bash
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

**Servidor local** — vista idéntica a producción, recomendado:

```bash
python -m http.server 8000     # → http://localhost:8000
# o
npx serve .
```

El origen `file://` bloquea algunas features del navegador. Si algo se ve raro al abrir el archivo directo, levantá el servidor antes de asumir que es un bug.

---

## Despliegue

GitHub Pages desde la rama principal, carpeta raíz. Cualquier `push` publica en segundos.

```
Settings → Pages → Source: Deploy from a branch · main · / (root)
```

**Dominio propio:** el sitio se sirve desde `lex.industrialnodes.com`, un subdominio apuntado a GitHub Pages por CNAME. El archivo `CNAME` en la raíz del repo lo genera GitHub y no debe borrarse: sin él, el dominio deja de resolver en el siguiente despliegue.

| Tipo | Nombre | Valor |
|---|---|---|
| CNAME | `lex` | `lexmoibusiness-stack.github.io` |

---

## Contacto

- **Email:** lex@industrialnodes.com
- **WhatsApp:** [+58 424 292 19 42](https://wa.me/584242921942)
- **Agenda:** [calendly.com/lex-moi-business/30min](https://calendly.com/lex-moi-business/30min)
- **LinkedIn:** [/in/lex-moi](https://www.linkedin.com/in/lex-moi)
- **Producto:** [industrialnodes.com](https://industrialnodes.com)

---

## Licencia

El código de este repositorio es de uso libre como referencia técnica. El contenido, los textos, la identidad visual y los casos de cliente no lo son.
