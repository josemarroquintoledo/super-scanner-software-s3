Super Scanner Software (S3)
===========================

Super Scanner Software (S3) is an **open-source and completely free software environment to implement a low-cost scanner 3D** that is also a **microscope and a 3D printer**. S3 is part of [**Super Scanner**](http://www.superscanner.cl) project.

To obtain high-quality and Hi-Res images, [**Super Scanner**](http://www.superscanner.cl) implements the [Fourier Ptychography](https://sites.google.com/site/gazheng/Fourier-Ptychograph) algorithm.

![Lo-Res and Low-Quality Image Set](img/for-doc/EN_set-n9-256x171_fly-wing_flickr.jpg)

![Reconstruction in High-Quality and Hi-Res](https://github.com/josemarroquintoledo/super-scanner-software-s3/blob/master/img/for-doc/EN_Hi-Res_fly-wing_flickr_wide_2304x685.jpg)

Software Requirements
---------------------

> **Note:** the correct functioning of these Jupyter modules has been tested in machines that run the 64-bit version of **[Linux Mint 18 'Sarah'](https://www.linuxmint.com/rel_sarah_cinnamon_whatsnew.php)** and **[budgie-remix](https://budgie-remix.org)**, which is based on **[Ubuntu 16.04.1 LTS](https://wiki.ubuntu.com/XenialXerus/ReleaseNotes?_ga=1.19022523.2089693014.1474004057)**.

S3 is a set of Python modules to be executed in notebook [Jupyter](http://jupyter.org) and [Blender](https://www.blender.org). For now, it is sufficient that you install:

- [**Anaconda3 (Python 3.5) 4.1.1**](https://www.continuum.io/downloads).

- [**Blender 2.77a**](https://www.blender.org/download/). It does not require to be installed: download it, untar it and execute it. It also be installed from the command-line with ``$ sudo apt-get install blender``.

Folders' Description
--------------------
Within the main folder, **super-scanner-software-s3**:

- **blend-meshes**: **printable parts and pieces** of Super Scanner Hardware (S2H) and the complete model to manipulate it in Blender are here.

- **blend-scripts**: it contains Python **scripts to be imported and executed directly in Blender**. Those files **simulate the scanner's structure and some tasks** such as the taking low resolution photographs with a different LED of the grid for the subsequent call of the Fourier Ptychography.

- **jupyter-modules**: it has **Python modules written as Jupyter notebooks**. With those, it is possible to reconstruct the Hi-Res image from the sample from a Lo-Res image set.

- **img**: it has some images files to be used by [fwdimaging.ipynb](jupyter-modules/fwdimaging.ipynb)

- **stl**: some models to use within the Blender scripts.

Importing and Executing the Code
--------------------------------

### In Jupyter

> **Note:** after the installation of [**Anaconda3](https://www.continuum.io/downloads), navigate to [autostart](jupyter-modules/autostart) (jupyter-modules&rarr;autostart) and follow the instructions of the notebooks there.

In the main folder, there is a **sample notebook**: [examples.ipynb](examples.ipynb). In any notebook, a cell is executed from **Cells**&rarr;**Run Cell** or with <kbd>Shift</kbd> &#43; <kbd>Enter</kbd>. Remember to run the notebook server from the command line with:

```
$ jupyter notebook examples.ipynb
```

### In Blender

The files within **blend-scripts** can be imported in Blender from **Choose Screen layout**&rarr;**Scripting**&rarr;<kbd>Open</kbd>. To execute them, press <kbd>Run Script</kbd> button and wait for the result.

#### Execute Blender code in a Jupyter notebook

[panzy](https://github.com/panzi) provides a [respository](https://github.com/panzi/blender_ipython) to run Blender script in Jupyter notebooks. Before to follow the instructions from [there](https://github.com/panzi/blender_ipython), **make sure you installed the dependences**. Anaconda3 does not resolve them.

```
$ sudo pip3 install ipython notebook
```

References
----------

Dong, S. Guo, K. Nanda, P. Shiradkar, R. & Zheng, G. (2014). FPscope: a field-portable high-resolution microscope using a cellphone lens. *Biomed. Opt. Express, 5*, 3305-3310.

Zheng, G. Ou, X. Hortsmeyer, R. Chung, J. & Yang, Ch. (2014). Fourier Ptychographic Microscopy: A Gigapixel Superscope for Biomedicine. *Optics & Photonics News, 25*, 26-33.

Zheng, G. (2015). *Fourier Ptychographic Imaging: A MATLAB® tutorial*. San Rafael, CA: Morgan & Claypool Publishers.

Dong, S. (2014). *Development of Gigapixel Microscopy*. Retrieved from http://digitalcommons.uconn.edu/gs_theses/687/

> **Note:** the image set and the reconstructed image at the beginning were obtained with `phaseretrieval.get_photo(n=9, sim=True, ampitude='img/BobMachines_microscopy-043--fly-wing_flickr_1024x685.tif')`.
