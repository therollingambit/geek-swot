# geek-swot-backend
A learning management system backend with Django and Django-REST-Framework

### create virtual environment
- in terminal, run `virtualenv .venv`
- activate venv with `source .venv/bin/activate`
- to deactivate venv, run `deactivate`

### install python packages
pip install
- django
- django-restframework
- django-cors-headers
- djoser (for authentication)
run `pip list` to see all packages installed

### create Django project
- run `django-admin startproject geekswot_django .`

### configure project
- in settings.py, add in INSTALLED_APPS:
  * `rest_framework`
  * `rest_framework.authtoken`
  * `corsheaders`
  * `djoser`
- add `CORS_ALLOWED_ORIGINS = ['http://localhost:8080',]`
- in MIDDLEWARE, add:
  * `corsheaders.middleware.CorsMiddleware`
- in urls.py, add:
  * `path('api/v1/', include('djoser.urls')),`
  * `path('api/v1/', include('djoser.urls.authtoken')),`

### init database
- in terminal, run `python manage.py makemigrations`
- next, run `python manage.py migrate`
- this will create a *db.sqlite3* file
