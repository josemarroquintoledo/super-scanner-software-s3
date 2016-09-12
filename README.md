Super Scanner Software (S3)
===========================

Super Scanner Software (S3) is an **open-source and completely free software environment to implement a low-cost microscopy**, which uses [Fourier Ptychography](https://sites.google.com/site/gazheng/Fourier-Ptychograph) algorithm, as a **3D scanner**. S3 is part of [**Super Scanner**](http://www.superscanner.cl) project.

Software Requirements
---------------------

> **Note:** currently, we are in the development phase and building the environment in machines that run the 64-bit version of **[Linux Mint 18 'Sarah'](https://linuxmint.com/download.php)** with MATE. As this GNU/Linux distribution **is based on another**, it is very probable that these packages work in your installation update to its latest version.

S3 is a set of Python modules to be executed in notebook [Jupyter](http://jupyter.org) and [Blender](https://www.blender.org). For now, it is sufficient that you install:

- [**Anaconda3 (Python 3.5) 4.1.1**](https://www.continuum.io/downloads).

- [**Blender 2.77a**](https://www.blender.org/download/). It does not require to be installed: download it, untar and execute it.

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

In the main folder, there is a **sample notebook**: [examples.ipynb](examples.ipynb). In any notebook, a cell is executed from **Cells**&rarr;**Run Cell** or with <kbd>Shift</kbd> &#43; <kbd>Enter</kbd>. Remember to run the notebook server from the command line with:

```
$ jupyter notebook examples.ipynb
```

> **Note**: ours notebook import others as modules. To get that feature in your Jupyter installation, follow the instructions in [98-jupyter-nb-import.ipynb](jupyter-modules/autostart/98-jupyter-nb-import.ipynb)

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
