# New Transport Quoter — Manual de Usuario

Documentacion oficial del sistema de cotizacion de transporte de carga, generada con [MkDocs](https://www.mkdocs.org/) y publicada automaticamente en GitHub Pages.

---

## Requisitos previos

- Python 3.10 o superior
- pip

---

## Ejecucion local

### 1. Crear y activar un entorno virtual

```bash
python -m venv venv
source venv/bin/activate   # macOS/Linux
# venv\Scripts\activate    # Windows
```

### 2. Instalar dependencias

```bash
pip install -r requirements.txt
```

### 3. Levantar el servidor de desarrollo

```bash
mkdocs serve
```

El sitio estara disponible en [http://localhost:8000](http://localhost:8000).
Los cambios en los archivos `docs/` se recargan automaticamente.

### 4. Generar el sitio estatico (opcional)

```bash
mkdocs build --clean
```

El resultado se genera en el directorio `site/`.

---

## Estructura del proyecto

```
.
├── docs/                  # Fuentes de la documentacion (Markdown)
│   ├── img/               # Capturas de pantalla
│   ├── cotizacion/        # Modulo de Cotizacion
│   ├── tarifas/           # Variables de Cotizacion
│   └── index.md           # Pagina de inicio
├── mkdocs.yml             # Configuracion de MkDocs
├── requirements.txt       # Dependencias Python
└── site/                  # Sitio compilado (generado por CI)
```

---

## Despliegue en GitHub Pages

El despliegue es **automatico** mediante GitHub Actions cada vez que se hace push a la rama `main`.

### Como funciona el flujo CI/CD

El workflow `.github/workflows/deploy.yml` ejecuta los siguientes pasos:

1. **Actualiza la version** — reemplaza el numero de version en `docs/index.md` y `mkdocs.yml` con la fecha actual en formato `YYYY.MM.DD`.
2. **Compila el sitio** — ejecuta `mkdocs build --clean` y genera el directorio `site/`.
3. **Commitea los cambios** — agrega `site/`, `docs/index.md` y `mkdocs.yml` al repositorio con el mensaje `ci: actualizar sitio y version [skip ci]`.
4. **GitHub Pages** sirve el contenido desde la rama `main`, directorio raiz (`/`).

### Configuracion requerida en el repositorio

En **Settings → Pages** del repositorio, configurar:

| Campo | Valor |
|---|---|
| Source | `Deploy from a branch` |
| Branch | `main` |
| Folder | `/site` |

> El directorio `site/` generado por CI es el que GitHub Pages sirve como raiz del sitio.

### Despliegue manual (sin CI)

Si se necesita publicar manualmente sin pasar por CI:

```bash
# 1. Compilar el sitio
mkdocs build --clean

# 2. Commitear y pushear el directorio site/
git add site/
git commit -m "docs: actualizar sitio"
git push origin main
```

---

## Versionado automatico

La version del documento se actualiza automaticamente en cada push a `main` con el formato `YYYY.MM.DD` (fecha UTC del dia del despliegue).

El valor se actualiza en dos lugares:

- `docs/index.md` — entre los marcadores `<!-- VERSION -->` y `<!-- /VERSION -->`
- `mkdocs.yml` — campo `extra.version`

---

Elaborado por **Boxting Labs**.
