# :scroll: Django Cheat Sheet
A concise cheat-sheet for creating web apps with the Django framework using the Python language. For the full documentation for Django v2.0 go to https://docs.djangoproject.com/en/2.0/.

## :snake: Initializing pipenv (optional)
- Make main folder with `$ mkdir <folder>` and navigate with `$ cd <folder>`
- Initialize pipenv with `$ pipenv install`
- To specify the python version `$ pipenv --python 3.6`
- Enter pipenv shell with `$ pipenv shell`
- Install django with `$ pipenv install django`
- Install other package dependencies with `$ pipenv install <package_name>`

## :blue_book: Creating a project
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

## :page_with_curl: Creating an app
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
