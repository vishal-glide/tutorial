# Django REST Framework Tutorial

My take on the DRF tutorial

## Steps to run

1. Once cloned, `cd` into the project root directory'
2. Create a virtual environment to isolate our package dependencies locally, using the following commands
   1. `python3 -m venv env`
   2. `source env/bin/activate` On windows, use `env\Scripts\activate`
   3. `pip install django`
   4. `pip install djangorestframework`
3. Now sync your database for the first time
   1. `python manage.py migrate`
4. We'll also create an initial user named `<username>` with a password `<password>`. We'll authenticate as that user later.
   1. `python manage.py createsuperuser --email <email_id> --username <username>`
5. Once done, we are ready to start the server with the following command
    - `python manage.py runserver`
6. Open a web-browser with the following url - http://127.0.0.1:8000/
   1. login with the credentials configured in step 4
7. You may now browse/test the apis

## Reading / Understanding Points

- Change to PostgreSQL from SQLite
- Read about django.contrib.auth.models
- Understand the purpose of serializers
  - HyperlinkedModelSerializer
- Primary key relationship could've been used instead of hyperlinking. But HyperLinking provides good RESTful design, why?
- Grouping together of common views together in viewsets. Read a bit on viewsets
- Permission_classes?
- Read about router classes
- auto-generation of urlconf due to usage of viewsets instead of views and registering  those with a router class. Read a bit more
- Read a bit about settings.py file - AUTH_PASSWORD_VALIDATORS, INSTALLED_APPS, 
- PageNumberPagination options