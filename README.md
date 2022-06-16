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

## Reading / Understanding / TODO Points

- ~~Change to PostgreSQL from SQLite~~
- ~~Read about django.contrib.auth.models~~
  - Serves as a means to implement user authentication with groups, roles, perms.
  - Also, has a lot of helpful classes like - `Group, AnonymousUser, UserManager, Validator, Permission` to better manage authentication flow.
  - Helpful link - [User Authentication in Django](https://docs.djangoproject.com/en/4.0/topics/auth/#)
- ~~Understand the purpose of serializers~~
  - Serializers in DRF are used in-place of Models in Django. They help convert complex data objects in to Python native objects and vice-versa. Serializers can be extended, overridden for behavioral fine-tuning.
  - Validators can be used with Serializers to validate fields or do combined-field validations. Reusable custom validators can be created in a special inner-class -> `Meta class`. E.g. UniqueValidator.
  - Helpful link - [DRF Serializers](https://www.django-rest-framework.org/api-guide/serializers/#serializers)
  - ~~Why HyperlinkedModelSerializer ?~~
    - Uses Hyper links instead of PKs to represent relationships. The url field will be represented using a HyperlinkedIdentityField serializer field, and any relationships on the model will be represented using a HyperlinkedRelatedField serializer field
- Primary key relationship could've been used instead of hyperlinking. But HyperLinking provides good RESTful design, why?
  - [Google: API links vs keys: Why you should use links, not keys, to represent relationships in APIs
  ](https://cloud.google.com/blog/products/application-development/api-design-why-you-should-use-links-not-keys-to-represent-relationships-in-apis)
  - [Microsoft: RESTful web API design](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)
- ~~Grouping together of common views together in viewsets. Read a bit on viewsets~~
  - Repeated logic can be combined into a single class. In the above example, we only need to specify the queryset once, and it'll be used across multiple views. 
  - By using routers, we no longer need to deal with wiring up the URL conf ourselves.
  - Helpful link - [Viewsets in DRF](https://www.django-rest-framework.org/api-guide/viewsets/#viewsets)
- ~~Permission_classes?~~ **DONE**
  - Check **User Authentication in Django** link given above.
- ~~Read about router classes~~
  - Link - [DRF Routers](https://www.django-rest-framework.org/api-guide/routers/)
- ~~auto-generation of urlconf due to usage of viewsets instead of views and registering  those with a router class. Read a bit more~~
  - Answered in the link above - **DRF Routers**
- Read a bit about settings.py file - AUTH_PASSWORD_VALIDATORS, INSTALLED_APPS,
  - Link - [DRF Settings](https://www.django-rest-framework.org/api-guide/settings/)
- PageNumberPagination options
  - Link - [DRF Pagination](https://www.django-rest-framework.org/api-guide/pagination/#pagination)