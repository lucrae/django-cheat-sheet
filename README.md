
# :scroll: Django Cheat Sheet
A concise cheat-sheet for creating web apps with the Django framework using the Python language. For the full documentation for Django v2.0 go to https://docs.djangoproject.com/en/2.0/.

## Sections
- [:snake: Initializing pipenv (optional)](#snake-initializing-pipenv-optional)
- [:blue_book: Creating a project](#blue_book-creating-a-project)
- [:page_with_curl: Creating an app](#page_with_curl-creating-an-app)
- [:tv: Creating a view](#tv-creating-a-view)
- [:art: Templates](#art-templates)


## :snake: Initializing pipenv (optional)
- Make main folder with `$ mkdir <folder>` and navigate to it with `$ cd <folder>`
- Initialize pipenv with `$ pipenv install`
- To specify the python version use `$ pipenv --python 3.6` within the directory
- Enter pipenv shell with `$ pipenv shell`
- Install django with `$ pipenv install django`
- Install other package dependencies with `$ pipenv install <package_name>`

## :blue_book: Creating a project
- Navigate to main folder with `$ cd <folder>`
- Create project with `$ django-admin startproject <project_name>`

The project directory should look like this:
```
project/
    manage.py
    project/
        __init__.py
        settings.py
        urls.py
        wsgi.py
```
- Run the development server with `$ python manage.py runserver` within the project directory
- To secure the secret key, open `settings.py` from the project directory
- Within this file, change the SECRET_KEY line to the following:
```python
SECRET_KEY = os.environ.get('SECRET_KEY')
```
- This defines the SECRET_KEY from an envrionment variable, set this with `$ export SECRET_KEY=<secret_key>`

## :page_with_curl: Creating an app
- Navigate to the project folder with  `$ cd <project_folder>`
- Create app with  `$ python manage.py startapp <app_name>`
- Inside the `app` folder, create a file called `urls.py`

The project directory should now look like this:
```
project/
    manage.py
    db.sqlite3
    project/
        __init__.py
        settings.py
        urls.py
        wsgi.py
    app/
	    migrations/
		    __init__.py
		__init__.py
		admin.py
	    apps.py
		models.py
		tests.py
		urls.py
		views.py
```

## :tv: Creating a view
- Within the app directory, open `views.py` and add the following:
```python
from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello, World!")
```
- Still within the app directory, open (or create)  `urls.py` 
```python
from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
```
- Now within the project directory, edit `urls.py` to include the following
```python
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('app/', include('app.urls')),
    path('admin/', admin.site.urls),
]
```
- To create a url pattern to the index of the site, use the following urlpattern:
```python
urlpatterns = [
    path("", include('app.urls')),
]
```
- Remember: there are multiple files named `urls.py`
- The `urls.py` file within app directories are organized by the `urls.py` found in the project folder.

## :art: Templates
- Within the app directory, files are located within the following locations:
```
app/
   templates/
      index.html
   static/
      style.css
      script.js
```
- To add a template to views, open `views.py` within the app directory and include the following:
```python
from django.shortcuts import render

def index(request):
    return render(request,'template_name.html')
```
- To include context to the template:
```python
def index(request):
	context = {"context_variable": context_variable}
    return render(request,'template_name.html', context)
```
