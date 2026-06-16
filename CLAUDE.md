# Contexto del proyecto

Este repositorio es parte del trabajo de desarrollo orientado a integrarse eventualmente con la **Intranet ZYMO** (zymointranet.com). Las reglas globales de desarrollo (código limpio, uso de skills, propuestas de mejora, deuda técnica, separación de tecnologías) están definidas en `~/.claude/CLAUDE.md` y aplican aquí también.

Aquí se construyen **templates y rutas de referencia en HTML, CSS y JavaScript separados** (nunca HTML monolítico con CSS/JS embebido) que luego el equipo de desarrollo e innovación de la empresa portará al stack real de cada backend/frontend de la intranet.

Antes de empezar cualquier tarea en este repo, lee `DEUDA_TECNICA.md`.

## Stack tecnológico — ZYMO Intranet (referencia, no se usa directamente en este repo)

### Infraestructura

| Capa          | Tecnología                            |
|---------------|----------------------------------------|
| Contenedores  | Docker Compose                         |
| Proxy         | Nginx (puerto 81)                      |
| OS destino    | Ubuntu 24.04                           |
| Dominio       | Cloudflare Tunnel → zymointranet.com   |
| CI/CD         | Webhooks                               |

### Frontend (`/frontend`) — puerto 81

| Categoría      | Tecnología |
|-----------------|------------|
| Framework       | React 19 + TypeScript ~5.9 |
| Build tool      | Vite 8 |
| Estilos         | TailwindCSS 3.4 + tailwindcss-animate + @tailwindcss/typography |
| State           | Zustand 5 |
| Data fetching   | TanStack Query 5 (React Query) + Axios 1.14 |
| Routing         | React Router DOM 7 |
| UI Primitives   | Radix UI (Avatar, Dialog, Dropdown, Label, Select, Separator, Slot, Tabs, Tooltip) |
| Drag & Drop     | @dnd-kit (core, sortable, utilities) |
| Gráficas        | Recharts 3 |
| Iconos          | Lucide React |
| Fechas          | date-fns 4 + react-day-picker 10 |
| Markdown        | react-markdown 10 + remark-gfm |
| Utilidades CSS  | clsx + tailwind-merge + class-variance-authority |
| Fuentes UI      | DM Sans + DM Mono (Google Fonts) |
| Linting         | ESLint 9 + eslint-plugin-react-hooks + eslint-plugin-react-refresh + typescript-eslint |

### Backend principal (`/backend`) — puerto 8001

| Categoría      | Tecnología |
|-----------------|------------|
| Runtime         | Python |
| Framework       | FastAPI 0.135 |
| Servidor ASGI   | Uvicorn 0.42 |
| ORM             | SQLModel 0.0.38 + Pydantic 2.12 |
| Base de datos   | SQLite (dev) / PostgreSQL (prod) |
| Auth            | JWT HS256 vía python-jose + bcrypt |
| Email           | fastapi-mail |
| Docs            | python-docx, WeasyPrint, Jinja2 |
| PDF/OCR         | pdfplumber, Pillow, pytesseract |
| Excel           | openpyxl |
| IA / LLMs       | Anthropic SDK (anthropic>=0.40) |
| Agentes         | APScheduler (cron de agentes) |
| Worker          | Proceso separado `zymo-worker` |

### helix-backend (`/helix-backend`) — puerto 3001

| Categoría      | Tecnología |
|-----------------|------------|
| Runtime         | Node.js + TypeScript 5.6 |
| Framework       | Express 4 |
| ORM             | Prisma 5 |
| Base de datos   | PostgreSQL 15 (puerto 5433) |
| Auth            | jsonwebtoken |
| Uploads         | Multer |
| Cron            | node-cron |
| Validación      | Zod |

### task-backend (`/task-backend`) — puerto 3002

| Categoría      | Tecnología |
|-----------------|------------|
| Runtime         | Node.js + TypeScript 5.6 |
| Framework       | Express 4 |
| ORM             | Prisma 5 |
| Base de datos   | PostgreSQL 15 (puerto 5434) |
| Auth            | jsonwebtoken |
| Email           | Nodemailer |
| Uploads         | Multer |
| Cron            | node-cron |
| PDF             | PDFKit |
| Excel           | ExcelJS |
| Validación      | Zod |
| HTTP client     | Axios |

### sig-backend (`/sig-backend`) — puerto 3004

| Categoría      | Tecnología |
|-----------------|------------|
| Runtime         | Node.js + TypeScript 5.6 |
| Framework       | Express 4 |
| ORM             | Prisma 5 |
| Base de datos   | PostgreSQL 15 (puerto 5436) |
| Auth            | jsonwebtoken |
| Email           | Nodemailer |
| Diffs           | diff (comparación de commits/documentos) |
| Validación      | Zod |

## Skills instaladas en este repo (`.claude/skills/`)

- `find-skills`
- `mcp-builder`
- `agent-browser`
- `web-design-guidelines`
- `frontend-design`

## Recordatorio de rol

Solo orientas en desarrollo. El control del proyecto es del usuario: sigue sus decisiones, potencia sus ideas, y recomienda la mejor práctica técnica en cada paso (diseño, seguridad, mantenibilidad), apoyándote en las skills y conectores disponibles.
