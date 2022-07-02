Preprocessing
===============================

.. code-block:: python

	def normalize_channel(img, lower=1, upper=99):
	    non_zero_vals = img[np.nonzero(img)]
	    percentiles = np.percentile(non_zero_vals, [lower, upper])
	    if percentiles[1] - percentiles[0] > 0.001:
		img_norm = exposure.rescale_intensity(img, in_range=(percentiles[0], percentiles[1]), out_range='uint8')
	    else:
		img_norm = img
	    return img_norm.astype(np.uint8)
  
In this tutorial you will create a documentation project on Read the Docs
by importing an Sphinx project from a GitHub repository,
tailor its configuration, and explore several useful features of the platform.

.. code-block:: python

	def create_interior_map(inst_map):
	    """
	    Parameters
	    ----------
	    inst_map : (H,W), np.int16
		DESCRIPTION.
	    Returns
	    -------
	    interior : (H,W), np.uint8 
		three-class map, values: 0,1,2
		0: background
		1: interior
		2: boundary
	    """
	    # create interior-edge map
	    boundary = segmentation.find_boundaries(inst_map, mode='inner')
	    boundary = morphology.binary_dilation(boundary, morphology.disk(1))

	    interior_temp = np.logical_and(~boundary, inst_map > 0)
	    # interior_temp[boundary] = 0
	    interior_temp = morphology.remove_small_objects(interior_temp, min_size=16)
	    interior = np.zeros_like(inst_map, dtype=np.uint8)
	    interior[interior_temp] = 1
	    interior[boundary] = 2
	    return interior

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
