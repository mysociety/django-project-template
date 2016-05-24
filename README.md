This project is intended to be a template to base mySociety Django projects on.
It is not meant to be deployable on its own.

Set up from a fresh empty repository:

You need django to use the template
    $ VIRTUALENV_PATH=../virtualenv-project_name
    $ virtualenv $VIRTUALENV_PATH
    $ source $VIRTUALENV_PATH/bin/activate
    $ pip install Django

Now you can create the project
    $ django-admin.py startproject --template=https://github.com/mysociety/django-jumpstart/archive/master.zip --extension py,yml,bash,conf-example,yml-example --name Vagrantfile project_name .
    $ pip install -r requirements.txt

And finally, start the vm that will run everything:
    $ vagrant up

(Make a cup of tea, it will take a while)

You will need to edit the .gitignore to ignore the normal deployed general and
httpd.conf files.

You might want to think about adding commonlib as a submodule.

Then when adding an app, use:

    ./manage.py startapp --template=<path-to-app_template-directory> app_name

Possible todo
-------------

* mySociety banner to the header/footer
* 404 and 500 templates

