# Website-django
Django was created in the fall of 2003, when the web programmers at the Lawrence Journal-World newspaper, Adrian Holovaty and Simon Willison, began using Python to build applications. Jacob Kaplan-Moss was hired early in Django's development shortly before Simon Willison's internship ended.
It was released publicly under a BSD license in July 2005. The framework was named after guitarist Django Reinhardt.
In June 2008, it was announced that a newly formed Django Software Foundation (DSF) would maintain Django in the future.

Django is a Python-based free and open-source web framework that follows the model-template-views (MTV) architectural pattern.It is maintained by the Django Software Foundation (DSF), an American independent organization established as a 501(c)(3) non-profit.

Django's primary goal is to ease the creation of complex, database-driven websites. The framework emphasizes reusability and "pluggability" of components, less code, low coupling, rapid development, and the principle of don't repeat yourself.

Python is used throughout, even for settings, files, and data models. Django also provides an optional administrative create, read, update and delete interface that is generated dynamically through introspection and configured via admin models.

This project is a bootstrap website built by django.

Create virtualenv:
1. pip install virtualenv #Install virtualenv
2. Virtualenv venv #Creates Virtualenv
3. venv\Scripts\activate #To activate virtualenv or use workon command to activate it in Bash

# Process Flow/Procedures
## mysite structure
1. django-admin startproject mysite.
The above command sets up a project directory in the name "mysite".
Refer to the mysite folder structure.
Mention the subapps created using "startapp" command in (3.) below name in settings.py file.

2. python manage.py runserver
To perform all system checks.

3. python manage.py startapp myapp.
Refer to the myapp folder structure.
Mention "myapp" in "INSTALLED APPS" section in settings.py(mysite folder).

## myapp structure

4. Create models with customization requirements in models.py.
Note: Refer Django documentation while declaring the type of fields in models.py.

5. Register models in admin.py file and run the below commands.
Python manage.py makemigrations
This creates table for DB for required model fields to store the data.

Python manage.py migrate
This provides space to accumulate the data into the DB mentioned in models.py.

6. Write the codes in views.py to fetch the DB data to the endpoint.

7. Write the codes in urls.py(myappp folder) to route the DB data to create an endpoint 

8. Map it to urls.py in "mysite" folder's urls.py via regular expressions.
Start the server and check whether all the apps are synchronized and are working simultaneously.

## Deployment
 We can deploy the apps built in django in Pythonanywhere, Heroku, Centos, Digital Ocean, AWS and many more platforms.
 I would prefer the deployment in pythonanywhere as below-
 
 1. Setting up your Web app and WSGI file on pythonanywhere
 Select a python web framework and set it to "Manual configurations"
 
 Edit your WSGI file
 One thing that's important here: your Django project (if you're using a recent version of Django) will have a file inside it called wsgi.py. This is not the one you need to change to set things up on PythonAnywhere -- the system here ignores that file.
 
 Instead, the WSGI file to change is the one that has a link inside the "Code" section of the Web tab -- it will have a name something like /var/www/yourusername_pythonanywhere_com_wsgi.py or /var/www/www_yourdomain_com_wsgi.py
 
 Click on the WSGI file link, and it will take you to an editor where you can change it.
 
 Delete everything except the Django section and then uncomment that section. Your WSGI file should look something like this:
 

## To use your own Django app use code like this:
import os
import sys

# assuming your Django settings file is at '/home/myusername/mysite/mysite/settings.py'
path = '/home/myusername/mysite'
if path not in sys.path:
    sys.path.insert(0, path)

os.environ['DJANGO_SETTINGS_MODULE'] = 'mysite.settings'

## Uncomment the lines below depending on your Django version
###### then, for Django >=1.5:
from django.core.wsgi import get_wsgi_application
application = get_wsgi_application()
###### or, for older Django <=1.4
#import django.core.handlers.wsgi
#application = django.core.handlers.wsgi.WSGIHandler()

Be sure to substitute the correct path to your project, the folder that contains manage.py, which you noted above.

Don't forget to substitute in your own username too!

Also make sure you put the correct value for DJANGO_SETTINGS_MODULE.

Save the file, then go and hit the Reload button for your domain. (You'll find one at the top right of the wsgi file editor, or you can go back to the main web tab).

Refer Django documentation if required.

2. Set Debug = False, Allowed host = ['*'] in settings.py file.
 
3.Set the Virtualenv path, source code path, working directory path.
 
 
 



