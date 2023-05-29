Masterclass 3: EM Modelling
===========================

.. image:: figures/delphi-logo.png
   :width: 400px
   :target: https://www.delphi-consortium.com/
   :alt: Delphi-Consortium


**2023 Delphi Meetings in Houston & The Hague**


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
exploration.


Structure of this Masterclass
-----------------------------

- Introduction ('30)
 
  - `Pre-requisites to run the examples <#pre-requisites-to-run-the-examples>`_
  - EM in Exploration Geophysics in 10 Minutes
  - `Codes, their manuals and galleries <#codes-their-manuals-and-galleries>`_

- Modelling with ``empymod`` ('30)

- Modelling with ``emg3d`` ('30)


- `Further links <#further-links>`_


Pre-requisites to run the examples
----------------------------------

- In this Masterclass we will use **Python** within **Jupyter Notebooks**.

- For scientific computations I always advice **against** using your PC's Python installation; you should use **dedicated Python installations** for your coding.

- For various reasons I also advice to use **Mambaforge**, or alternatively the regular *conda*.

Local Installation
''''''''''''''''''

1. Download and install the corresponding Mambaforge for your OS:  
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

I will use Python 3.11. However, Python 3.7-3.11 *should* work; earlier
versions might work, but potentially with older versions of the packages.

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
  have to login in order to run it.

- .. image:: https://jupyterlite.rtfd.io/en/latest/_static/badge-launch.svg
     :target: https://emsig.xyz/emlite
     :alt: JupyterLite

  JupyterLite: I transferred some of the notebooks (the computationally light
  ones) to JupyterLite. JupyterLite is a static website with client-side
  computation. You can run everything in it without installing anything at all.
  Just be aware that everything happens in the cache of your browser. If you
  clean the cache, your stuff is gone.

Codes, their manuals and galleries
----------------------------------

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


Further links
-------------


empymod/emg3d with inversion frameworks
'''''''''''''''''''''''''''''''''''''''

- SimPEG(emg3d): `curvenote.com/@prisae/emg3d-as-solver-for-simpeg/hackathon-emg3d-inversion-in-simpeg <https://curvenote.com/@prisae/emg3d-as-solver-for-simpeg/hackathon-emg3d-inversion-in-simpeg>`_
- pyGIMLi(empymod): `github.com/gimli-org/transform2021 -> 6_Inversion_with_any_forward_operator.ipynb <https://github.com/gimli-org/transform2021/blob/main/6_Inversion_with_any_forward_operator.ipynb>`_


DISC 2017 & em-apps
'''''''''''''''''''

- Website: `disc2017.geosci.xyz <https://disc2017.geosci.xyz>`_
- SEG info: `seg.org/Education/Courses/DISC/2017-DISC-Doug-Oldenburg <https://seg.org/Education/Courses/DISC/2017-DISC-Doug-Oldenburg>`_
- Repo `github.com/geoscixyz/em-apps <https://github.com/geoscixyz/em-apps>`_


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

- **Marine Electromagnetic Methods - Beginnings to Today** by *Steve
  Constable*: `Video <https://www.youtube.com/watch?v=UITjv78w9z4>`_;
  `Slides <https://mtnet.info/EMinars/20211027_Constable_EMinar.pdf>`_.

- **Multi-physics analysis: Extracting the most from diverse datasets** by
  *Lucy MacGregor*: `Video <https://youtu.be/mBd8tizMigE>`_;
  `Slides <https://mtnet.info/EMinars/20210714_MacGregor_EMinar.pdf>`_.

- **Fundamentals of Inversion** by *Douglas Oldenburg*:
  `Video <https://youtu.be/YHhugJICXl4>`_;
  `Slides <https://mtnet.info/EMinars/20210303_Oldenburg_EMinar.pdf>`_.

- **custEM**: by *Raphael Rochlitz*:
  `Video <https://youtu.be/c_pHSD_ZyS8>`_;
  `Slides <https://mtnet.info/EMinars/20220316_Rochlitz_EMinar.pdf>`_.
