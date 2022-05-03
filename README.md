# Django-Rest-React-MySQL
Demo Django Rest Framework with Reactjs and Mysql on window
 
I. Documentation

    1. Overview https://docs.djangoproject.com/en/4.0/intro/overview
        - Install package: Installation: https://docs.djangoproject.com/en/4.0/topics/install/#installing-distribution-package
        - Install on window: https://docs.djangoproject.com/en/4.0/howto/windows
        
    2. Python tutorial: https://docs.python.org/3/tutorial/controlflow.html
    
    3. Django Rest Framework: Django REST framework is a powerful and flexible toolkit for building Web APIs
       https://www.django-rest-framework.org
 


II. Installation

    1. Setting up a virtual environmen
       - https://docs.djangoproject.com/en/4.0/howto/windows/#install-python-windows
       - Cmd: ...\> py -m venv project-name & ...\> project-name\Scripts\activate.bat

    2. Create DjangoAPI
        - https://docs.djangoproject.com/en/4.0/ref/django-admin
        - Install: py -m pip install Django
        - Create backend: django-admin startproject DjangoAPI
        - Run cmd in backend to start the project: "py manage.py runserver"
        - Open the link http://127.0.0.1:8000 on the browser.

    3. Config file settings.py   
        - Add 'rest_framework' to your INSTALLED_APPS setting.
        - Add 'corsheaders' and middleware (https://pypi.org/project/django-cors-headers)
        - Config MySQL:
            + Install pyMysql: https://pypi.org/project/PyMySQL/#installation
            import pymysql
            pymysql.install_as_MySQLdb()
            DATABASES = {
                'default': {
                    'ENGINE': 'django.db.backends.mysql',
                    'NAME': 'django_react_mysql',
                    'USER':'root',
                    'PASSWORD':'',
                    'HOST':'localhost',
                    'PORT':'3306'
                }
            }
    4. startapp
        https://docs.djangoproject.com/en/4.0/ref/django-admin/
        - Run cmd:  "django-admin startapp backend" and add 'backend' to your INSTALLED_APPS setting.
        - Create new file (copy) urls.py in backend folder to override url backend.
        - Add 2 models "Departemnts", "Employees" in file models.py. 
        - Run cmd: "py manage.py makemigrations backend". Let's check folder migrations, the app will create new file '0001_inital.py'. Then run cmd "py manage.py migrate backend" to migration all tables.

        - Run "python manage.py migrate" to use User authentication in Django (if have issue, let's try run on other tool)
        - Create super admin cmd: py manage.py createsuperuser backend --email admindjangoreact@yopmail.com --username admin
        -> On the site http://localhost:8000/admin. Login pass: 123!@#***

        - In file DjangoApi/urls.py add 'api/' and open the site http://127.0.0.1:8000/api/
            urlpatterns = [
                path('admin/', admin.site.urls),
                path('api/', include('backend.urls')),
            ]
