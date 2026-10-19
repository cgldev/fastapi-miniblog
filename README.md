# FastAPI Mini Blog

API REST para gestionar publicaciones de un blog. Es un proyecto de aprendizaje y portfolio que evoluciona junto con los módulos de desarrollo backend.

## Funcionalidades implementadas actualmente

- Crear, listar, consultar, actualizar y eliminar publicaciones.
- Buscar publicaciones por título.
- Paginar resultados y ordenar por identificador o título.
- Filtrar publicaciones por una o más etiquetas.
- Asociar opcionalmente un autor y etiquetas a una publicación.
- Validar datos de entrada mediante Pydantic.
- Manejar respuestas HTTP para recursos no encontrados y errores de persistencia.
- Documentación interactiva generada por FastAPI.

## Tecnologías

- Python
- FastAPI
- Pydantic v2
- SQLAlchemy 2
- SQLite para desarrollo local
- python-dotenv para configuración mediante variables de entorno

## Estructura principal

```text
app/
├── main.py
├── core/
│   └── db.py
├── models/
│   ├── author.py
│   ├── post.py
│   └── tag.py
└── api/
    └── v1/
        └── posts/
            ├── router.py
            ├── repository.py
            └── schemas.py
```

## Requisitos

Python 3.10 o superior. Las dependencias están declaradas en `requirements.txt`.

## Instalación en Windows (PowerShell)

Desde la raíz del repositorio:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Si necesitás usar variables de entorno, copiá `.env.example` como `.env` y ajustá los valores para tu entorno. No subas el archivo `.env` a GitHub.

## Ejecutar la API

```powershell
fastapi dev app/main.py
```

Abrí la documentación interactiva en `http://127.0.0.1:8000/docs`.

## Endpoints actuales

| Método | Ruta | Propósito |
|---|---|---|
| `GET` | `/posts` | Listar publicaciones, con búsqueda, paginación y orden |
| `GET` | `/posts/by-tags` | Filtrar publicaciones por etiquetas |
| `GET` | `/posts/{post_id}` | Consultar una publicación; permite omitir el contenido |
| `POST` | `/posts` | Crear una publicación |
| `PUT` | `/posts/{post_id}` | Actualizar una publicación |
| `DELETE` | `/posts/{post_id}` | Eliminar una publicación |

## Estado del proyecto

Esta es la versión inicial publicada del proyecto. La autenticación JWT, la gestión independiente de usuarios/categorías/etiquetas, los slugs, las migraciones con Alembic, PostgreSQL y el despliegue son trabajo futuro y no se presentan aquí como funcionalidades ya implementadas.

Actualmente, la aplicación crea las tablas al iniciar, una solución de desarrollo que se revisará al incorporar migraciones.

## Objetivo educativo

El repositorio acompaña el aprendizaje de desarrollo de APIs REST y se ampliará con commits pequeños y coherentes a medida que se implementen nuevas funcionalidades. Cada commit documentará un cambio real en el código.

## Autor

César Gimenez Lascano — [@cgldev](https://github.com/cgldev)
