======================
DDEX Reader for Python
======================

.. image:: https://travis-ci.org/Trax-air/ddexreader.svg
        :target: https://travis-ci.org/traxair/ddexreader

.. image:: https://img.shields.io/pypi/v/ddexreader.svg
        :target: https://pypi.python.org/pypi/ddexreader

.. image:: https://coveralls.io/repos/Trax-air/ddexreader/badge.svg?branch=master&service=github
        :target: https://coveralls.io/github/Trax-air/ddexreader?branch=master


This project allows you to read DDEX files into friendly Python data types. XML files are decoded using the PyXB
library.

Keep in mind that this is a fairly low level library that only aims at making DDEX files easier to read using Python. Some DDEX data structures expose lists containing only one element, and some value like UpdateIndicator are not cast as booleans.

* Free software: MIT license
* Documentation: https://ddexreader.readthedocs.org.
* Repository: https://github.com/Trax-air/ddexreader

Features
--------

* Open an XML file into a DDEX data structure generated by pyxb corresponding to the DDEX version.
* Parse this DDEX data structure into a Python dict.

Supported DDEX versions
-----------------------

* 3.2 (untested)
* 3.3
* 3.4
* 3.4.1
* 3.5
* 3.5.1
* 3.6

Version 3.7 is causing issues with PyXB.

Quickstart
----------

::

  from ddexreader import open_ddex, ddex_to_dict

  xml_path = '/path/to/my/ddex_file.xml'
  ddex = open_ddex(xml_path)
  ddex_dict = ddex_to_dict(ddex)

How to add more DDEX definitions
--------------------------------

After installing pyxb on your (unix) system, enter:

::

  pyxbgen -u [the url to the definition file]
