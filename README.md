# Library Project API

<img width="1200" height="900" alt="ScreenShot" src="https://github.com/user-attachments/assets/63200faa-6daf-4300-8ba6-f571c5618408" />




A Django REST Framework-based API for managing a library system with books and related functionality.

## Project Structure

```
library_project/          # Main Django project settings
├── settings.py          # Django configuration
├── urls.py              # Project URL routing
├── asgi.py              # ASGI configuration
└── wsgi.py              # WSGI configuration

books/                    # Books app
├── models.py            # Book models
├── views.py             # API views
├── serializers.py       # DRF serializers
├── urls.py              # App URL routing
├── admin.py             # Django admin configuration
└── templates/
    └── index.html       # Frontend template
```

## Requirements

- Python 3.x
- Django 5.2.14
- Django REST Framework 3.17.1
- SQLite3 (default database)

## Installation

1. **Create and activate virtual environment:**
   ```bash
   python -m venv ds
   # On Windows:
   .\ds\Scripts\Activate.ps1
   # On macOS/Linux:
   source ds/bin/activate
   ```

2. **Install dependencies:**
   ```bash
   pip install django djangorestframework
   ```

3. **Apply migrations:**
   ```bash
   python manage.py migrate
   ```

## Running the Project

Start the development server:
```bash
python manage.py runserver
```

The API will be available at `http://127.0.0.1:8000/`

### Available Endpoints

- API documentation: `http://127.0.0.1:8000/api/`
- Admin panel: `http://127.0.0.1:8000/admin/`

## Development

### Create a Superuser

```bash
python manage.py createsuperuser
```

Then log in to the admin panel at `http://127.0.0.1:8000/admin/`

### Create Migrations

After modifying models:
```bash
python manage.py makemigrations
python manage.py migrate
```

### Run Tests

```bash
python manage.py test
```

## Database

The project uses SQLite by default (stored in `db.sqlite3`). This is suitable for development but not recommended for production.

For production, consider using PostgreSQL or MySQL by updating `DATABASES` in `settings.py`.

## Notes

- **Development Server**: The current server is for development only. Use a production WSGI server (Gunicorn, uWSGI) for deployment.
- **Static Files**: Run `python manage.py collectstatic` before deploying.
- **Secret Key**: Make sure to change the `SECRET_KEY` in `settings.py` for production.

## License

MIT
