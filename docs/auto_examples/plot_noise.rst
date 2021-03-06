

.. _sphx_glr_auto_examples_plot_noise.py:

 
Adding noise to the input
=========================

Example usage of the AddNoise augmentation.
 




.. image:: /auto_examples/images/sphx_glr_plot_noise_001.png
    :align: center





.. code-block:: python

    import sys
    import numpy as np
    from scipy.ndimage import imread
    import matplotlib.pyplot as plt

    from astronet.augmentations import AddNoise

    X = np.ones((4,1,50,50))*10
    y = np.ones(4)

    augment = AddNoise(scale=[0,100])
    Xtransformed, _, _ = augment.apply(X, y, None)

    fig, ax = plt.subplots(len(X),2, figsize=(4,8), squeeze=False, 
                           subplot_kw={'xticks': [], 'yticks': []})
    ax[0][0].set_title("Before")
    ax[0][1].set_title("After")
    for i in range(len(X)):
        ax[i][0].imshow(X[i][0])
        ax[i][1].imshow(Xtransformed[i][0])

**Total running time of the script:** ( 0 minutes  0.272 seconds)



.. container:: sphx-glr-footer


  .. container:: sphx-glr-download

     :download:`Download Python source code: plot_noise.py <plot_noise.py>`



  .. container:: sphx-glr-download

     :download:`Download Jupyter notebook: plot_noise.ipynb <plot_noise.ipynb>`

.. rst-class:: sphx-glr-signature

    `Generated by Sphinx-Gallery <http://sphinx-gallery.readthedocs.io>`_
