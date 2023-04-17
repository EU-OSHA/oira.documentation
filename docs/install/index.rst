Installation
============

The *Online interactive Risk Assessment tool (OiRA)* is an adaptation of 
`Euphorie`_, which is an add-on product for the `Plone`_ content management
system.

Minimum recommended system requirements for running an OiRA site are::

* Ubuntu 18.04 LTS or 22.04 LTS
* Python 3.8
* Postgresql 10+
* Git
* Nginx

Install Python 3.8 on Ubuntu 18.04
----------------------------------

Python 3.8 isn't available by default on Ubuntu 18.04 but it can be installed from a ppa::

  $ sudo apt update
  $ sudo apt install software-properties-common
  $ sudo add-apt-repository ppa:deadsnakes/ppa
  $ sudo apt install python3.8
  $ sudo apt install python3.8-dev
  $ sudo apt install python3.8-venv


Install other system requirements
---------------------------------
::

  $ sudo apt install build-essential
  $ sudo apt install postgresql
  $ sudo apt install git

Instalation of OiRA software with buildout
------------------------------------------

OiRA uses zc.buildout for installation and configuration.
First clone the git repo::

  $ git clone git@github.com:EU-OSHA/oira.application.buildout.git
  $ cd oira.application.buildout

Add a buildout.cfg file to configure the software as you require, for example::

  [buildout]
  extends =
      production_zeo.cfg

  [settings]
  postgres-url = postgresql://username:password@localhost/database
  # configure the postgresql server details above, as appropriate

  [supervisor]
  programs =
      10 zeo ${zeo:location}/bin/runzeo ${zeo:location}
      100 zope ${buildout:directory}/bin/instance [console] ${instance:location} true

Create a python virtual environment with python3.8::

  $ python3.8 -m venv py3

Now, you can run `make` to complete the installation of the OiRA software.

Start the Services
------------------

Supervisor is used to manage the services::

  $ ./bin/supervisord

Check the current status of the services::

  $ ./bin/supervisorctl status
  zeo                              RUNNING   pid 14377, uptime 0:00:07
  zope                             RUNNING   pid 14378, uptime 0:00:07

Configuration
-------------

Euphorie uses the Plone registry to handle application configuration. All values use the prefix ``euphorie``.

Some notable options are:

   +---------------------------------------+-----------------------------------------------+
   | options                               | Description                                   |
   +=======================================+===============================================+
   | ``euphorie.client_url``               | URL for the client (see also                  |
   |                                       | `Virtual hosting`_).                          |
   +---------------------------------------+-----------------------------------------------+
   | ``euphorie.library``                  | Path (inside Plone) to a sector that          |
   |                                       | should be used as the Library of OiRA  tools. |
   +---------------------------------------+-----------------------------------------------+
   | ``euphorie.max_login_attempts``       | Number: after how many failed login attempts  |
   |                                       | in the client the user account gets locked.   |
   +---------------------------------------+-----------------------------------------------+
   | ``euphorie.allow_guest_accounts``     | Boolean: If enabled the feature for guest     |
   |                                       | login is available in the client.             |
   +---------------------------------------+-----------------------------------------------+
   | ``euphorie.allow_user_defined_risks`` | Boolean: If enabled the feature for creating  |
   |                                       | custom riks is available in the client.       |
   +---------------------------------------+-----------------------------------------------+

Google analytics
----------------

Euphorie includes complete Google Analytics support. However due to data protection
regulations, this feature is not available in OiRA.

.. _piwik:

Web analytics (Piwik)
---------------------

`Plone by default can be configured <http://docs.plone.org/adapt-and-extend/config/site.html>`_
to include a block of Javascript code on every page for logging information to a
web analytics tool such as Piwik. The OiRA client and admin interface make use of
this option. That means to enable Piwik tracking, the appropriate Javascript (available
from the Piwik installation) needs to be pasted into the field "Javascript for
web statistics support" of the Plone installation.

SQL database
------------

Euphorie uses a SQL database to store information for users of the client. Any
SQL database supported by SQLALchemy_ should work. If you have selected a
database you will need to configure it in ``buildout.cfg``. 
Postgresql is supported by default, so the python psycopg_ driver is already installed.

Next you need to configure the database connection information. 
This is done via the settings section of the buildout.cfg file, as already mentioned above::

  [settings]
  postgres-url = postgresql://username:password@localhost/database

Make sure The ``url`` parameter is correct for the database you want to use.
It uses the standard SQLAlchemy connection URI format.

To setup the database you must run buildout and run the database initialisation
command::

    $ ./py3/bin/buildout
    $ bin/instance initdb  
  

.. _virtualhosting:

Virtual hosting
---------------

Euphorie requires two separate virtual hosts: one host for the client, and one
for CMS tasks. It is common to use ``oira.example.com`` as hostname for the
client and ``admin.oira.example.com`` as hostname for the CMS. The standard
method for configuring virtual hosting for Plone sites applies here as well. 
The Plone website has instructions for `configuring Plone with Nginx`_.
Here is an example Nginx configuration::

  server {
    listen 443 ssl http2;
    server_name oira.example.com;

    ssl_certificate /etc/letsencrypt/live/oira.example.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/oira.example.com/privkey.pem;

    location ~ ^(.*)$ {
        rewrite ^(.*)$ /VirtualHostBase/$scheme/oira.example.com:$server_port/Plone/VirtualHostRoot$1;
        proxy_pass http://127.0.0.1:8080;
        break;
    }
  }
  server {
    listen 443 ssl http2;
    server_name admin.oira.example.com;

    ssl_certificate /etc/letsencrypt/live/admin.oira.example.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/admin.oira.example.com/privkey.pem;

    location ~ ^(.*)$ {
        rewrite ^(.*)$ /VirtualHostBase/$scheme/admin.oira.example.com:$server_port/Plone/VirtualHostRoot$1;
        proxy_pass http://127.0.0.1:8080;
        break;
    }
  }

You will also need to configure the URL for the client in the portal_registry: "euphorie.client_url".

.. _usage_statistics:

Usage Statistics
----------------

To generate usage statistics reports a `Metabase`_ server needs to be set up.
It must be configured using `oira.statistics.deployment`_. Its SQL database URL
needs to be made available via the osha.oira product configuration. This can be
done through buildout with the `zope-conf-additional` option::

    [instance]
    ...
    zope-conf-additional =
        <product-config osha.oira>
            postgres-url-statistics postgresql://XXXX:XXXX@localhost/{database}
        </product-config>

Do not replace the `{database}` placeholder. This is done by the application on-the-fly.

.. _Euphorie: https://pypi.python.org/pypi/Euphorie
.. _Plone: https://plone.org/
.. _SQLAlchemy: https://sqlalchemy.org/
.. _psycopg: https://www.psycopg.org/
.. _configuring Plone with Nginx: https://docs.plone.org/manage/deploying/front-end/nginx.html
.. _zopyx.smartprintng.server: https://pypi.python.org/pypi/zopyx.smartprintng.server
.. _Prince XML: http://www.princexml.com/
.. _oira.statistics.deployment: https://github.com/EU-OSHA/oira.statistics.deployment
.. _Metabase: https://www.metabase.com/
