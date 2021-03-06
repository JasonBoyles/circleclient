============
circleclient
============

.. image:: https://travis-ci.org/qba73/circleclient.svg?branch=master
    :target: https://travis-ci.org/qba73/circleclient
    :alt: Travis CI Build Status

.. image:: https://pypip.in/v/circleclient/badge.png
    :target: https://pypi.python.org/pypi/circleclient
    :alt: Latest Version

.. image:: https://pypip.in/d/circleclient/badge.png
    :target: https://pypi.python.org/pypi/circleclient
    :alt: Downloads

.. image:: https://pypip.in/license/circleclient/badge.png
    :target: https://pypi.python.org/pypi/circleclient/
    :alt: License

Python client library for CircleCI API.

Features
========

* Retrieve information about user
* List followed repositories
* Start build
* Create parametrized builds
* List build artifacts
* Cancel build
* Retry build
* Clear build cache


Installation
============

.. code:: python

    pip install circleclient


Usage
=====

Retrieve information about User
-------------------------------

.. code:: python

    import os
    import circleclient


    token = os.environ['API_TOKEN']
    client = circleclient.CircleClient(token)

    # Retrieve User data
    client.user.info()


List projects followed by the user
----------------------------------

.. code:: python

   import os
   import circleclient


   token = os.environ['API_TOKEN']
   client = circleclient.CircleClient(token)

   # Retrieve information about projects
   client.projects.list_projects()


Trigger new build
-----------------

.. code:: python

   import os
   import circleclient

   token = os.environ['API_TOKEN']
   client = circleclient.CircleClient(token)

   # Trigger build
   client.build.trigger('<username>', '<project_name>', '<branch>')


Trigger new parametrized build
------------------------------

.. code:: python

   import os
   import circleclient

   token = os.environ['API_TOKEN']
   client = circleclient.CircleClient(token)

   # Trigger parametrized build
   client.build.trigger('<username>', '<project_name>', '<branch>', '<PARAM1>'='<VAL1>')


Retrieve build status
--------------------

.. code:: python

   import os
   import circleclient

   token = os.environ['API_TOKEN']
   client = circleclient.CircleClient(token)

   # Retrieve build status
   client.build.status('<username>', '<project_name>', '<build_number>')


Cancel running build
--------------------

.. code:: python

   import os
   import circleclient

   token = os.environ['API_TOKEN']
   client = circleclient.CircleClient(token)

   # Cancel build
   client.build.cancel('<username>', '<project_name>', '<build_number>')


Retry build
-----------

.. code:: python

   import os
   import circleclient

   token = os.environ['API_TOKEN']
   client = circleclient.CircleClient(token)

   # Retry build
   client.build.retry('<username>', '<project_name>', '<build_number>')


List build artifacts
--------------------

.. code:: python

   import os
   import circleclient

   token = os.environ['API_TOKEN']
   client = circleclient.CircleClient(token)

   # List build artifacts
   client.build.artifacts('<username>', '<project_name>', '<build_number>')


Clear build cache
-----------------

.. code:: python

   import os
   import circleclient

   token = os.environ['API_TOKEN']
   client = circleclient.CircleClient(api_token=token)

   # Clear build cache
   client.cache.clear(username='<username>', project='<project_name>')
