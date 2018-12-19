

* SITE URL: http://18.205.163.5.xip.io/
* Public IP: 18.205.163.5
* Port: 2200


installations:

* python2.7 
sudo apt-get install python

* pip
sudo apt-get install pip

* apache2
sudo apt-get install apache2

* postgresql
sudo apt-get install postgresql

* flask
pip2 install flask

* flask_login
pip2 install flask_login

* sqlalchemy
pip2 install sqlalchemy

* urllib2
pip2 install urllib2

* rauth
pip2 install rauth

* virtualenv
pip install virtualenv



configuration files:

* catalog.conf in apache2
------------------

<VirtualHost *:80>
    ServerName 18.205.163.5
    ServerAlias 18.205.163.5.xip.io
    ServerAdmin grader@18.205.163.5
    WSGIDaemonProcess catalog python-path=/var/www/catalog:/var/www/catalog/venv/lib/python2.7/site-packages
    WSGIProcessGroup catalog
    WSGIScriptAlias / /var/www/catalog/catalog.wsgi
    <Directory /var/www/catalog/catalog/>
        Order allow,deny
        Allow from all
    </Directory>
    Alias /static /var/www/catalog/catalog/static
    <Directory /var/www/catalog/catalog/static/>
        Order allow,deny
        Allow from all
    </Directory>
    ErrorLog ${APACHE_LOG_DIR}/error.log
    LogLevel warn
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>



*catalog.wsgi in /var/www/catalog/
------------------

import sys
import logging
logging.basicConfig(stream=sys.stderr)
sys.path.insert(0, "/var/www/catalog/")

from catalog import app as application
application.secret_key = 'top secret!'


SUDO
* user: grader
* password: udacity


Third party resources:
* My Discord Partner In Meme: Rasta#7493
* A few udacity videos
* College
* https://github.com/rrjoson

