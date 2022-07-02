Preprocessing
===============================

.. code-block:: python

	from mpl_toolkits.basemap import Basemap
	import matplotlib.pyplot as plt

	map = Basemap(projection='aeqd', lon_0 = 10, lat_0 = 50)

	print map(10, 50)
	print map(20015077.3712, 20015077.3712, inverse=True)
  
  
In this tutorial you will create a documentation project on Read the Docs
by importing an Sphinx project from a GitHub repository,
tailor its configuration, and explore several useful features of the platform.

The tutorial is aimed at people interested in learning
how to use Read the Docs to host their documentation projects.

Getting started
---------------

Preparing your project on GitHub
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

(or the one of your choosing).
This is the repository you will import on Read the Docs,
and it contains the following files:


Sign up for Read the Docs
~~~~~~~~~~~~~~~~~~~~~~~~~
