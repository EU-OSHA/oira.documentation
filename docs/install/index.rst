Installation
============


The OiRA application, which is visible to the user via client and admin interface,
requires a number of different components. Apart from the basic Plone installation,
this includes the web-server and caching setup, as well as external components
used for creating PDF files or reports of usage statistics.

To get an overview of the different components and their basic installation,
please refer to :ref:`manual_installation`.

Getting all components to work together seamlessly, spread over different
(virtual) hosts, is not trivial, especially if the required configuration is
kept in many different locations. Therefore, the production and staging installation
of OiRA make use of the configuration- and deployment tool `batou`_. This is
described in :ref:`batou`.


.. toctree::
   :maxdepth: 2

   manual
   batou/index


.. _batou: https://batou.readthedocs.io/en/latest/
