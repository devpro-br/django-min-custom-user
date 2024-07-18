# django-min-custom-user
A project with a mininum fields Django Custom User

## How to use

Install the lib

```bash
pip install django_min_custom_user
```

Create an app:

```
python manage.py custom_user_app
```

Add the app to INSTALLED_APPS on settings.py:

```python
INSTALLED_APPS = [
    ...,    
    'custom_user_app',
]

```

Create your custom User:

```
from django_min_custom_user.models import MinAbstractUser


class User(MinAbstractUser):
    pass

```
This user has all fields from regular Django users but username and last_name.

Set your customized User on DJango settings.py:

```
AUTH_USER_MODEL = 'custom_user_app.User'
```

Customize also your User Admin:

```
from django_min_custom_user.admin import MinUserAdmin


class UserAdmin(MinUserAdmin):
    pass
```

Now run and apply migration:

```
python manage.py makemigrations
python manage.py migrate
```
Check django_project_ex for an example of Django project using above configurations.

