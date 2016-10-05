.. OiRA Documentation documentation master file, created by
   sphinx-quickstart on Tue Jun  7 15:56:51 2016.

.. _index:

******************************************************
:mod:`OiRA` -- Online Interactive Risk Assessment tool
******************************************************

.. ToDo List
.. =========

.. This must be empty before we are done.

.. .. todolist::


About
=====

OIRA is a tool for risk assessment. It is developed by `SYSLAB`_ and `TNO`_
in cooperation with `Simplon`_ and `Cornelis Kolbach`_ in commission of
`The European Agency for Safety and Health at Work`_ (EU-OSHA) as part of the
`Healthy Workplaces`_ campaign. The software base package is called `Euphorie`_
and is also used by the Dutch `RIE`_ project. Adaptations of the software version that is used by EU-OSHA are found in the package `osha.oira <https://pypi.python.org/pypi/osha.oira>`_.

.. _syslab: http://syslab.com/
.. _TNO: http://www.tno.nl/index.cfm?Taal=2
.. _Simplon: http://www.simplon.biz/
.. _Cornelis Kolbach: http://www.cornae.com
.. _The European Agency for Safety and Health at Work: http://osha.europa.eu/en/
.. _Healthy Workplaces: http://osha.europa.eu/en/campaigns/hw2008
.. _Euphorie: https://pypi.python.org/pypi/Euphorie/
.. _RIE: http://instrumenten.rie.nl/


The OiRA risk assessment tool is based on hierarchical questionnaires. A
questionnaire (referred to as OIRA tool) covers most of the possible risks for a specific sector of
industry.

Each sector organisation can have one or more OiRA tools published simultaneously.
In order to facilitate development and testing of OIRA tools the system supports
multiple versions for OiRA tools. Only a single version of an OiRA tool can be public
at any point in time.


Technical Information
=====================

.. toctree::
   :maxdepth: 2

   install/index

.. toctree::
   :maxdepth: 1

   xml

.. toctree::
   :maxdepth: 3

   implementation/index

.. toctree::
  :hidden:

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

