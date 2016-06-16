.. _batou_components:

Batou Components
================

Zope
----

The Zope component builds the :ref:`plone_installation`.

.. autoclass:: components.zope.ZopeBase
.. autoclass:: components.zope.Zope
.. autoclass:: components.zope.ZopeCommunity

Zeo
---

Zeo allows to share the ZODB between multiple Zope instances.

.. autoclass:: components.zeo.ZEOBase
.. autoclass:: components.zeo.ZEO
.. autoclass:: components.zeo.ZEOCommunity


Birt
----

External dependencies:

* Apache Tomcat 6

The Birt component provides reporting capabilities for :ref:`usage_statistics`. It requires Apache Tomcat to be installed in the system. The BIRT webapp and the report files are automatically downloaded and installed by the component.

.. autoclass:: components.birt.Birt


Crontab
-------

External dependencies:

* Cron

.. autoclass:: batou.lib.cron.CronTab


Docs
----

.. autoclass:: components.docs.Docs


HAProxy
-------

External dependencies:

* HAProxy

The HAProxy component configures the load balancer.

.. autoclass:: components.haproxy.HAProxy


Logrotate
---------

External dependencies:

* Logrotate

.. autoclass:: batou.lib.logrotate.Logrotate


Nagios
------

External dependencies:

* Nagios

.. autoclass:: batou.lib.nagios.NRPEHost
.. autoclass:: batou.lib.nagios.NagiosServer


Nginx
-----

External dependencies:

* Nginx

The Nginx component takes care of :ref:`virtual_hosting`.

.. autoclass:: components.nginx.Nginx


Postgres
--------

External dependencies:

* PostgreSQL Server 9.x
* PostgreSQL JDBC driver

Postgres provides the :ref:`sql_database`.

.. autoclass:: components.postgres.Postgres


Settings
--------

.. autoclass:: components.settings.Settings


SmartprintNG
------------

The SmartprintNG component is responsible for :ref:`pdf_printing`.

.. autoclass:: components.smartprintng.SmartprintNG


Supervisor
----------

The Supervisor component manages running processes.

.. autoclass:: components.supervisor.Supervisor


Varnish
-------

External dependencies:

* Varnish

.. autoclass:: components.varnish.Varnish
