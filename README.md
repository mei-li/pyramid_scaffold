Pyramid Scaffold
================

Sample application to demostrate issue with Debugtoolbar paths when it runs with uwsgi.

Steps to reproduce
-----------------
- Follow the installation instructions below
- Run application with pserve (the paths on the toolbar left look fine)
- Run application with uwsgi (check below)
- Request paths all have the path `/_debug_toolbar/sse`

Installation
------------


- Create a Python virtual environment.

    `python3 -m venv env`


- Enable the environenment

    `source env/bin/activate`


- Upgrade packaging tools.

    `pip install --upgrade pip setuptools`


- Install the project in editable mode with its testing requirements.

    `pip install -e "."`


Run your project
----------------

    pserve development.ini

Run with uwsgi
--------------
For linux python3-dev package is required.


    pip install uwsgi

    uwsgi --http :6543 --ini-paste-logged development.ini 
