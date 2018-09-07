# Development Template

This repository hosts a Django template that is designed for rapid setup of local development installations.  It replaces the file `setup/default_setup.zip`, which was previously hosted in the [main project repository](https://github.com/django-danceschool/django-danceschool).

## How to use

For full deployment instructions, including more details potential customization of settings, see the [documentation](https://django-danceschool.readthedocs.io/en/latest/installation_development.html)

### You Will Need:

-  Python 3.4+ (it is recommended that you deploy in a virtual environment)
-  pip3: The Python package manager
-  External library dependencies for Pillow, used for basic image
   processing (see the [Pillow
   Documentation](http://pillow.readthedocs.io/en/3.4.x/installation.html)).
   
1. In your Python environment, install the django-danceschool app and all its
   necessary dependencies from [PyPi](https://pypi.python.org/pypi):

       pip3 install django-danceschool

2. Start your Django project, using the ``django-admin`` command.  To avoid
   having to set a large number of settings manually, we strongly recommend
   that you use the preexisting installation template as follows.  Make sure
   that you are in the folder where you would like your project to be located when you do this.

       django-admin startproject --template https://raw.githubusercontent.com/django-danceschool/development-template/archive/master.zip <your_project_name>

3. Perform initial database migrations
       
       cd <your_project_name>
       python3 manage.py migrate

4. Create a superuser so that you can log into the admin interface (you
   will be prompted for username and password)

       python3 manage.py createsuperuser

5. **Optional, but strongly recommended:** Run the easy-installer setup
   script, and follow all prompts.  This script will guide you through
   the process of setting initial values for many things, creating a few
   initial pages that many school use, and setting up user groups and
   permissions that will make it easier for you to get started running
   your dance school right away.

       python3 manage.py setupschool

6. Run the server and try to log in!

       python3 manage.py runserver

### Alternative Method (requires Git client)

1. Clone this repository:

       git clone https://github.com/django-danceschool/development-template.git

2. Use the Python package manager to install requirements:

       cd development-template
       pip3 install -r requirements.txt

2a. **Strongly recommended:** Update the value of ``SECRET_KEY`` in ``school/settings.py``
    to something strong and secret. This is absolutely necessary to ensure security if
    your development server is publicly accessible.

3. Proceed with steps 3-6 as above.
