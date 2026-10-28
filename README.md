# antony Parfum — Catálogo CRUD + API

Proyecto académico adaptado a la Guía 05. La interfaz utiliza una estética premium oscura con acentos dorados; la lógica conserva los tres campos que solicita la guía: `nombre`, `categoria` y `estado`.

## Requisitos
- Python 3.11 o 3.12
- MongoDB local, o una URI de MongoDB Atlas configurada como variable `MONGO_URI`

## Ejecutar en Windows (PowerShell, terminal de VS Code)
```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe app.py
```
Abre http://127.0.0.1:5000. La ayuda está en `/ayuda` y la API en `/api/productos`.

## API incluida
- `GET /api/productos`
- `GET /api/productos/ID`
- `POST /api/productos`
- `PUT /api/productos/ID`
- `DELETE /api/productos/ID`

JSON de ejemplo:
```json
{
  "nombre": "Oud Wood",
  "categoria": "Amaderada",
  "estado": "Disponible"
}
```

## Probar las cuatro operaciones
Deja `app.py` funcionando en una terminal y ejecuta en otra:
```powershell
.\.venv\Scripts\python.exe probar_api.py
```

## GitHub y Render
Crea un repositorio NUEVO para este proyecto, separado del repositorio de la plantilla. No subas `.env`, contraseñas ni `.venv`.
- Build Command: `pip install -r requirements.txt`
- Start Command: `gunicorn app:app --bind 0.0.0.0:$PORT --workers 1 --threads 4 --timeout 60`
- En Render agrega la variable `MONGO_URI` con la URI real de tu base de Atlas.

La aplicación usa la base `perfumeria_luxe` y la colección `productos`. Si tu profesor indicó un nombre distinto, cambia el nombre de la base en `app.py` y utiliza ese mismo nombre en Atlas.

**Importante:** la API de esta práctica no tiene inicio de sesión ni permisos. Usa únicamente datos ficticios.
