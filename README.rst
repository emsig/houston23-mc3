Masterclass 3: EM Modelling
===========================

.. image:: figures/delphi-logo.png
   :width: 400px
   :target: https://www.delphi-consortium.com/
   :alt: Delphi-Consortium


**2023 Delphi Meeting in Houston**


.. image:: https://mybinder.org/badge_logo.svg
   :target: https://mybinder.org/v2/gh/emsig/houston23-mc3/main
   :alt: MyBinder
.. image:: https://colab.research.google.com/assets/colab-badge.svg
   :target: https://colab.research.google.com/github/emsig/houston23-mc3
   :alt: Colab
.. image:: https://jupyterlite.rtfd.io/en/latest/_static/badge-launch.svg
   :target: https://emsig.xyz/emlite
   :alt: JupyterLite
.. image:: https://img.shields.io/github/license/emsig/houston23-mc3.svg
   :target: https://github.com/emsig/houston23-mc3/blob/main/LICENSE
   :alt: License

|

In the following 1.5 h we are going to use **empymod** and **emg3d** to model
electromagnetic data in the diffusive regime, as commonly used in geophysical
exploration. Most things I am going to talk about can be found in this README,
with links and pointers the used resources.


Outline of the class
--------------------

1. `Quick intro to EM in geophysics <#quick-intro-to-em-in-geophysics>`_
2. `Codes, their manuals and galleries <#codes-their-manuals-and-galleries>`_
3. `Pre-requisites to run the examples <#pre-requisites-to-run-the-examples>`_
4. `Modelling with empymod <#modelling-with-empymod>`_
5. `Modelling with emg3d <#modelling-with-emg3d>`_
6. `Further links <#further-links>`_


1. Quick intro to EM in geophysics
----------------------------------

The slides/notebooks (?) can be found in ???

TODOs
'''''

- Create updated figure of EM/Potential landscape/ecosystem; add ResIPy,
  EMagPy, MTpy, …
- Create slides
- Test-give the masterclass
- mention CLI
- mention IP, mu, epsilon, loops, ...
- mention SimPEG(emg3d), pyGIMLi(empymod/emg3d), JIF(empymod/emg3d)
- https://curvenote.com/@prisae/emg3d-as-solver-for-simpeg/hackathon-emg3d-inversion-in-simpeg


Notes
'''''

EM, in the frequency-range we generally use in exploration, is dominated by
diffusion. In contrast to seismic, we are limited in what we can do with
processing, such as migration. Instead, we depend on modelling and iterative
modelling, so called inversions, to try to figure out what is in the
subsurface. The tricky thing with this is of course that we do not do anything
with the measured data, but only with the model we are working with.

Today we will focus on forward modelling, and by the end of this Master Class
you should be able to forward model both semi-analytical data for layered
media, and data for a fully three-dimensional model.


**=> Bring a picture with the EM geophysics spectrum:**

DC/electrical resistivity - MT - CSEM - loops - GPR


empymod can do everything, but only for layered media. emg3d is more restricted to the CSEM/loops range; GPR would be difficult, as is DC.


Not so long ago EM codes were mostly restricted to big companies and research consortia such as Consortium for Electromagnetic Modeling and Inversion (CEMI). The well-know and widespread exceptions were:

- DIPOLE1D and MARE2DEM Kerry Key, Steven Constable, et al; Marine EM laboratory at Scripps Institution of Oceanography

However, in the past few years there was suddenly a wealth of open-source codes being released, which changed the landscape. The new thing is that many of these are not simply open-source, but it is an open community, where everyone is invited to participate, improve/evolve the code, and decide on its future path. And many of these communities are talking to each other, which gives for a very inspiring community!

- SimPEG
- pyGIMLi/custEM
- PETGEM

Slides (15 min)
'''''''''''''''

- Brief intro to EM
  - frequency ranges
  - applications
  - diffusion vs waves
- Methods and applications
  - CSEM, MT, TEM
  - land, air, water
- Landscape: emsig, SimPEG, pyGIMLi, Fatiando, custEM, PETGEM, ...
- Links (see below)
- Slides 4, 5, 7 of Raphaels EMinar
- Show documentation (on the web)
- Layered, 3D, give outline of what will come
  - empymod (30 min)
    - marine CSEM, f-domain
    - land CSEM, t-domain
    - airborne loops
    - quick sensitivity analysis
  - emg3d (45 min)
    - minimal example (just `solve`)
    - full-fledged simulation


2. Codes, their manuals and galleries
-------------------------------------

.. image:: https://raw.github.com/emsig/logos/main/empymod/empymod-logo.png
   :width: 400px
   :target: https://empymod.emsig.xyz
   :alt: empymod logo

Full 3D electromagnetic modeller for 1D VTI media.

- Manual: https://empymod.emsig.xyz
- Gallery: https://empymod.emsig.xyz/en/stable/gallery
- Code: https://github.com/emsig/empymod
- Installation: https://empymod.emsig.xyz/en/stable/manual/installation.html


.. image:: https://raw.github.com/emsig/logos/main/emg3d/emg3d-logo.png
   :width: 400px
   :target: https://emg3d.emsig.xyz
   :alt: emg3d logo

A multigrid solver for 3D electromagnetic diffusion.

- Manual: https://emg3d.emsig.xyz
- Gallery: https://emsig.xyz/emg3d-gallery/gallery
- Code: https://github.com/emsig/emg3d
- Installation: https://emg3d.emsig.xyz/en/stable/manual/installation.html


3. Pre-requisites to run the examples
-------------------------------------

- In this Masterclass we will use **Python** within **Jupyter Notebooks**.

- For scientific computations I always advice **against** using your PC's Python installation; you should use **dedicated Python installations** for your coding.

- For various reasons I also advice to use **Mambaforge**, or alternatively the regular *conda*.

Local Installation
''''''''''''''''''

1. Download and install the correct Mambaforge for your OS:  
   https://github.com/conda-forge/miniforge#mambaforge

   (Mambaforge uses mamba, the faster conda implementation, and sets
   conda-forge, the community maintained package repository, as default
   source.)

2. Download or clone the repo at https://github.com/emsig/houston23-mc3, and
   ``cd`` to the directory.

3. Install the environment with

   .. code-block:: python

       mamba env create -f environment.yml

   This will install an environment called ``houston23-mc3``.

4. Activate the environment with

   .. code-block:: python

       mamba activate houston23-mc3

5. Add this kernel to the recognized Jupyter kernels (optional, to have access
   from other envs as well) with

   .. code-block:: python

       python -m ipykernel install --user --name houston23-mc3

6. Start Jupyter Lab

   .. code-block:: python

        jupyter lab

The following google docs contains some further instructions, which might be
useful (particular for Windows users): https://swu.ng/t20-python-setup

I will use Python 3.9. However, Python 3.7-3.10 _should_ work; 3.11 will not
work (yet); earlier versions might work, but potentially with older versions of
the packages.

If you prefer to install the required packages in whatever other way, feel free
to do so. Here the packages lists:

- Required: ``empymod``, ``emg3d``, ``matplotlib``, ``discretize``, ``h5py``,
  ``pooch``, ``xarray``; ``ipyml`` (for interactive plots in the Jupyter lab).
- Optional: ``scooby``, ``mkl``, ``tqdm``.



Online
''''''

- .. image:: https://mybinder.org/badge_logo.svg
      :target: https://mybinder.org/v2/gh/emsig/houston23-mc3/main
      :alt: MyBinder

  MyBinder: I tested the repo on MyBinder, and it should work; however, be
  aware that it can take some time to start-up a virtual machine.

- .. image:: https://colab.research.google.com/assets/colab-badge.svg
     :target: https://colab.research.google.com/github/emsig/houston23-mc3
     :alt: Colab

  Google Colab: If you have a Google account you can also run it on Colab. You
  have to login in order to run it (TODO TEST).

- .. image:: https://jupyterlite.rtfd.io/en/latest/_static/badge-launch.svg
     :target: https://emsig.xyz/emlite
     :alt: JupyterLite

  JupyterLite: I transferred some of the notebooks (the computationally light
  ones) to JupyterLite. JupyterLite is a static website with client-side
  computation. You can run everything in it without installing anything at all.
  Just be aware that everything happens in the cache of your browser. If you
  clean the cache, your stuff is gone.


4. Modelling with empymod
-------------------------

See notebooks ... TODO

- 
- 

5. Modelling with emg3d
-----------------------

See notebooks ... TODO

- 
-

6. Further links
----------------

Software Underground (Swung) Transform Tutorials `swu.ng <https://swu.ng>`_
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

..
  swu.ng/t20-playlist; swu.ng/t21-playlist; swu.ng/t22-playlist

- SimPEG 2020: `youtu.be/jZ7Sj9cnnso <https://youtu.be/jZ7Sj9cnnso>`_
- SimPEG 2021: `youtu.be/5MiaebDwWUQ <https://youtu.be/5MiaebDwWUQ>`_
- pyGIMLi 2021: `youtu.be/w3pu0H3dXe8 <https://youtu.be/w3pu0H3dXe8>`_
- pyGIMLi 2022: `youtu.be/2Hu4gDnRzlU <https://youtu.be/2Hu4gDnRzlU>`_

EMinars `mtnet.info/EMinars <https://mtnet.info/EMinars/EMinars.html>`_
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

- custEM 2022: `youtu.be/c_pHSD_ZyS8 <https://youtu.be/c_pHSD_ZyS8>`_
  (slides: `mtnet.info/EMinars/20220316_Rochlitz_EMinar.pdf
  <http://mtnet.info/EMinars/20220316_Rochlitz_EMinar.pdf>`_)
