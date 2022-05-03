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

    1. Setting up a virtual environment (optional)
       - https://docs.djangoproject.com/en/4.0/howto/windows/#install-python-windows

    2. Create DjangoAPI
        - https://docs.djangoproject.com/en/4.0/ref/django-admin
        - Install: py -m pip install Django
        - Create backend: django-admin startproject DjangoAPI
        - Run cmd in backend to start the project: "py manage.py runserver"
        - Open the link http://127.0.0.1:8000 on the browser.

    3. Config file settings.py   
        - Add 'rest_framework', 'backend' to your INSTALLED_APPS setting.
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