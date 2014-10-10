Introduction
============

``bobtemplates.imio`` provides `mr.bob`_ templates to generate packages for
Plone projects.

This product is freely based on ``bobtemplates.ecreall``.

Usage
=====

Create a mr.bob virtualenv
--------------------------

::

  virtualenv-2.7 .
  bin/python bootstrap.py
  bin/buildout

Create your package
-------------------

::

  bin/mrbob -O collective.foo bobtemplates:cpskin_diazo_theme

See `mr.bob`_ documentation for further information : http://mrbob.readthedocs.org/en/latest/
