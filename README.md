# SR Tablet Interface

The interface for the tablets contained in the SR 2015 kit.

## Set up

External libraries are managed with `bower`, therefore you must have it installed and also make sure to install all the packages before testing:

    $ bower install

## Running

    $ pip install gunicorn Flask Flask-sockets
    $ gunicorn -k flask_sockets.worker runserver:app
