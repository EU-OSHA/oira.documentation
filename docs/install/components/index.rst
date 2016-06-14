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

The Birt component provides reporting capabilities for usage statistics.

.. autoclass:: components.birt.Birt


Crontab
-------

.. autoclass:: batou.lib.cron.CronTab


Docs
----

.. autoclass:: components.docs.Docs


HAProxy
-------

.. autoclass:: components.haproxy.HAProxy


Logrotate
---------

.. autoclass:: batou.lib.logrotate.Logrotate


Nagios
------

.. autoclass:: batou.lib.nagios.NRPEHost
.. autoclass:: batou.lib.nagios.NagiosServer


Nginx
-----

The Nginx component takes care of :ref:`virtual_hosting`.

.. autoclass:: components.nginx.Nginx


NRPE
----

.. autoclass:: batou.lib.nagios.NRPEHost


Postgres
--------

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

.. autoclass:: components.varnish.Varnish
