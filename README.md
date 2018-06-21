# Django Cheat-sheet
A concise cheat-sheet for creating web apps with the Django framework using Python.

Django v2.0 documentation: https://docs.djangoproject.com/en/2.0/

## Initializing pipenv (optional)
1. Navigate to project folder with `$ cd <project_folder>`
2. Initialize pipenv with `$ pipenv install`
3. Enter pipenv shell with `$ pipenv shell`
4. Install django with `$ pipenv install django`
5. Install other package dependencies with `$ pipenv install <package_name>`

## Creating a project
- Navigate to main folder with `$ cd <project_folder>`
- Create project with `$ django-admin startproject <project_name>`

The main folder should look like this:
```
project/
    manage.py
    project/
        __init__.py
        settings.py
        urls.py
        wsgi.py
```
- Run the development server with `$ python manage.py runserver`

## Creating an app
- Navigate to the project folder with  `$ cd <project_folder>`
- Create app with  `$ python manage.py startapp <app_name>`
- Inside the `app` folder, create a file called `urls.py`

The project folder should now look like this:
```
project/
    manage.py
    project/
        __init__.py
        settings.py
        urls.py
        wsgi.py
	app/
	    __init__.py
	    admin.py
	    apps.py
	    migrations/
	        __init__.py
	    models.py
	    tests.py
	    urls.py
	    views.py
```
