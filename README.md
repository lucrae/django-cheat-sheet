# :scroll: Django Cheat Sheet
A concise cheat-sheet for creating web apps with the Django framework using the Python language. For the full documentation for Django v2.0 go to https://docs.djangoproject.com/en/2.0/.

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
