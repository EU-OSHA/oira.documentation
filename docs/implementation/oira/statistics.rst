Statistics
**********

OiRA contains the capability of generating usage statistics reports. In
addition to a global overview there are reports on the country level as well as
for individual tools.

The admin interface has a page that redirects users to metabase, a database 
analysis tool which is configured to show statistics based on the collected 
database information.
The resulting report can be directly downloaded by the user. Metabase also allows 
further manipulation of the data for custom purposes.

The statistics feature uses a number of database tables in addition to the ones
defined in the online client's :ref:`schema_structure`:

.. graphviz:: statistics.dot

.. _report templates: https://github.com/EU-OSHA/oira.reports
.. _Metabase: http://www.metabase.com
