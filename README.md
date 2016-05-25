mySociety's Django project template
===================================

This is a template for creating Django projects (using [Django's facility for
such](https://docs.djangoproject.com/en/1.9/ref/django-admin/#cmdoption-startproject--template))
in a mySociety-ish way. It's probably not all that useful to you unless you
are a mySociety developer, or are interested in how we do things.

Usage
-----
Set up from a fresh empty repository (i.e. after you've done git init and
`cd`-ed into that new folder:

You need to install Django to use the template. We do that in a virtualenv
(replace project_name with whatever you want the top level name of your Django
project to be).

```
$ virtualenv ../virtualenv-project_name
$ source ../virtualenv-project_name/bin/activate
$ pip install Django
```

Now you can create the project (again, replace project_name with the real name):

```
$ django-admin.py startproject --template=https://github.com/mysociety/django-project-template/archive/master.zip --extension py,yml,bash,conf-example,yml-example --name Vagrantfile .gitignore-example project_name .
$ pip install -r requirements.txt
```

The project template includes a Vagrantfile to start your development
environment with the basics you need for a standard project (PostgreSQL, etc)
and a few extras like [mailcatcher](https://mailcatcher.me/) that make life
easier for development. To start that, type:

```
$ vagrant up
```

(Make a cup of tea, it will take a while)

Git ignores
-----------
You'll want to put a .gitignore in place for (at least) the various files
mySociety's deployment system creates. There's an example in .gitignore-example
which you can copy if you wish.

App template
------------
When adding an app, [we have another template for that](https://github.com/mysociety/django-app-template):

```
$ ./manage.py startapp --template=https://github.com/mysociety/django-app-template/archive/master.zip app_name
```
