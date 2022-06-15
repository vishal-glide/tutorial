# Django REST Framework Tutorial

My take on the DRF tutorial

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