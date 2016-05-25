[//]: # ({% comment "This weird comment is a hacky way to provide both a README for the template and a template for the README. Markdown will ignore this and Django's templating will ignore everything until the matching endcomment tag." %})

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
$ django-admin.py startproject --template=https://github.com/mysociety/django-project-template/archive/master.zip --extension py,yml,bash,conf-example,yml-example,md --name Vagrantfile project_name .
```

The project template includes a Vagrantfile to start your development
environment with the basics you need for a standard project (PostgreSQL, etc)
and a few extras like [mailcatcher](https://mailcatcher.me/) that make life
easier for development. To start that, type:

```
$ vagrant up
```

(Make a cup of tea, it will take a while)

App template
------------
When adding an app, [we have another template for that](https://github.com/mysociety/django-app-template):

```
$ ./manage.py startapp --template=https://github.com/mysociety/django-app-template/archive/master.zip app_name
```

README Generation
-----------------

The following Django template will be used to generate a basic README for your
project - you're encouraged to make it better!

[//]: # ({% endcomment %}you can delete this line, it's a hack from the project template)
{{ project_name|capfirst }}
===========================

[![Installability](http://img.shields.io/badge/installability-gold-ffd700.svg)]()

Put a top-level description of your project here.

Local development
-----------------

This project includes a Vagrantfile to make local development easy.
Simply run:

    $ vagrant up

To get a fully configured vagrant development environment. The code is
installed into `/vagrant/{{ project_name }}` inside the VM, and you can run
the Django dev server with:

    $ source virtualenv-{{ project_name }}/bin/activate
    $ python manage.py runserver 0.0.0.0:8000

The website will then be running at http://localhost:8000
