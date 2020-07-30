Pyramid Scaffold
================

Sample application to demostrate issue with Debugtoolbar paths when it runs with uwsgi.

Steps to reproduce
-----------------
- Follow installation instructions
- Run application with pserve (the paths on the toolbar left look fine)
- Run application with uwsgi (check below)
- Request paths all have the path `/_debug_toolbar/sse`

Getting Started
---------------

- Change directory into your newly created project.

    cd pyramid_scaffold

- Create a Python virtual environment.

    python3 -m venv env

- Upgrade packaging tools.

    env/bin/pip install --upgrade pip setuptools

- Install the project in editable mode with its testing requirements.

    env/bin/pip install -e ".[testing]"

- Initialize and upgrade the database using Alembic.

    - Generate your first revision.

        env/bin/alembic -c development.ini revision --autogenerate -m "init"

    - Upgrade to that revision.

        env/bin/alembic -c development.ini upgrade head

- Load default data into the database using a script.

    env/bin/initialize_pyramid_scaffold_db development.ini

- Run your project's tests.

    env/bin/pytest

- Run your project.

    env/bin/pserve development.ini

- Run with uwsgi

    pip install uwsgi
    uwsgi --http :6543 --ini-paste-logged development.ini 
