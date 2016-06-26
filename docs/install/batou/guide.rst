.. _batou:

Batou installation guide
========================

Preparation
-----------

As batou is a remote deployment tool, the machine you are deploying from is not necessarily the machine you are deploying to. We will call the machine you are deploying from your local machine. It will need network access (ssh in particular) to the host(s) you will be deploying to. Make sure this machine fulfils the `batou requirements`_. To run the master command on your machine you will need to have the following dependencies installed:

* Python 2.7
* virtualenv
* OpenSSH
* GPG (optional, if you want to use encrypted secrets support)
* Mercurial, git, or rsync (you only need to have the one installed you actually use to transfer your repository). OiRA is currently using mercurial.


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

The repository contains definitions of the individual OiRA components as well as environment definitions that assign combinations of components to hosts.

Create your environment
-----------------------

You will need two things to get started:

* An environment file.
  Create a file named oira.batou/envrionments/<dev-myname>.cfg. You may copy
  in the contents of oira.batou/environments/template-developer.cfg and adjust
  it to fit your needs.

* A secrets file.
  First, make sure that GPG is configured on you machine. Then you need can add
  a secrets file for your envrionment by executing
  cd oira.batou
  ./batou secrets <dev-myname>
  Editing your secrets at a later point works the same way. For the contents of
  the file, please refer to oira.batou/secrets/secrets-template.cfg. Once you
  have finished editing your file, it will be stored (encrypted) in
  oira.batou/secrets/<dev-myname>.cfg

You may now check in these two files.

There are separate environments for production and staging. Staging uses all the components that are present in production, but concentrates them on fewer hosts to save resources. Besides those two environments, there are a handful of additional ones for testing or local development.

If you want to create a new environment, you can take one of the existing ones (``oira.batou/environments/dev-*.cfg``) as a base and modify it accordingly.

 Further information can be found in the `oira.batou README`_ and the `batou quickstart`_.


Run batou
---------

* cd oira.batou
* ./batou local <dev-myname>.cfg

This will deploy your environment locally.

Note: If your host is NOT named localhost (the default hard-coded into batou),
you must use this call:

* ./batou local <dev-myname>.cfg <hostname>

where <environment> is the name of one of the files in the environments/ directory (with or without the *.cfg* extension), e.g. *production*. For a local deployment use ``batou local`` instead.

*Example*: A full deployment to staging is started by this command::

    ./batou remote staging.cfg



For the components that are defined by oira.batou see :ref:`batou_components`.


.. _oira.batou deployment code: https://bitbucket.org/oshahosting/oira.batou
.. _batou requirements: https://batou.readthedocs.io/en/latest/user/install.html#local
.. _batou quickstart: https://batou.readthedocs.io/en/latest/user/quickstart.html
.. _oira.batou README: https://bitbucket.org/oshahosting/oira.batou/src/bec1904ffeeabbd5c7b9ee20e60b5a400e7abb35/README.txt?fileviewer=file-view-default
