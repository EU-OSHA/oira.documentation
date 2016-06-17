.. _batou:

Batou installation guide
========================

Preparation
-----------

As batou is a remote deployment tool, the machine you are deploying from is not necessarily the machine you are deploying to. We will call the machine you are deploying from your local machine. It will need network access (ssh in particular) to the host(s) you will be deploying to. Make sure this machine fulfils the `batou requirements`_.

The host(s) you are deploying to will need the following installed:

* libffi (Foreign Function Interface library development files),
  e.g. on Debian/Ubuntu: ``sudo apt-get install libffi-dev``

Depending on the :ref:`components <batou_components>` selected in the batou environment (see below) you may also need some or all of the following:

* Nginx
* Varnish
* HAProxy
* PostgreSQL Server
* PostgreSQL JDBC driver
* Apache Tomcat
* Cron
* Mercurial
* Subversion
* SQLite


Setup
-----

Start by getting the `oira.batou deployment code`_ onto your local machine by cloning the mercurial repository::

    $ hg clone ssh://hg@bitbucket.org/gocept/oira.batou

The repository contains definitions of the individual OiRA components as well as environment definitions that assign combinations of components to hosts. If you want to create a new environment or modify an existing one please refer to the `oira.batou README`_ and the `batou quickstart`_. When creating a new development environment you can take one of the existing ones (``oira.batou/environments/dev-*.cfg``) as a base.

To start a remote deployment, run ``batou remote``::

    $ cd oira.batou
    $ ./batou remote <environment>

where <environment> is the name of one of the files in the environments/ directory (with or without the *.cfg* extension), e.g. *production*. For a local deployment use ``batou local`` instead.

For the components that are defined by oira.batou see :ref:`batou_components`.


.. _oira.batou deployment code: https://bitbucket.org/oshahosting/oira.batou
.. _batou requirements: https://batou.readthedocs.io/en/latest/user/install.html#local
.. _batou quickstart: https://batou.readthedocs.io/en/latest/user/quickstart.html
.. _oira.batou README: https://bitbucket.org/oshahosting/oira.batou/src/bec1904ffeeabbd5c7b9ee20e60b5a400e7abb35/README.txt?fileviewer=file-view-default
