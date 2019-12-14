# Intro-to-ExoCTK
An introduction to the Exoplanet Characterization Toolkit (ExoCTK) package and Web application

Installation
------------

The following are instructions on how to install the ``exoctk`` package for both users and contributors.  The ``exoctk`` repository provides a ``conda`` environment containing all of the dependencies needed to install and execute the ``exoctk`` software.

Download Anaconda or Miniconda
------------------------------

You must first have a working installation of ``anaconda`` or ``miniconda`` for Python 3.  If you do not yet have this on your system, you can visit the following links for download and installation instructions:

- `Anaconda <https://www.anaconda.com/download/>`_
- `Miniconda <https://conda.io/en/latest/miniconda.html>`_

Obtain the ``exoctk`` Package
-----------------------------

To obtain the ``exoctk`` package with the necessary environment files, clone the repository directly from GitHub:

::

  git clone https://github.com/ExoCTK/exoctk.git


ExoCTK Data
-----------
ExoCTK relies on a large collection of data. Some tools may be run entirely
without this data, but light curve fitting, observation planning, and our model
grid interfaces require this data. The full data package is 12GB, and can be
downloaded from MAST (FINDME / maybe.) If this is too large to fit on your
machine, we have a stripped down set of data that can get you through this
workshop, available here (FINDME / dropbox?) 

After downloading the data in some form, you will have a directory structure
with ``exoctk_data`` at the top level, and subdirectories that correspond to
module specific data, like ``groups_integrations``, ``fortney``, ``generic``,
and so on. Export an environment variable to point to this top level.

::

    export EXOCTK_DATA='/path/to/your/exoctk_data/'

This can be a command you run each time you use the package, or added to a
``.bashrc`` or ``.bash_profile``.

Environment Installation
-------------------------
You can install the ExoCTK ``conda`` environment via the ``env/environment-<PYTHON_VERSION>.yml`` files (relative to the parent directory of where the repository was installed).  Note that there are separate environment files for each version of ``python`` that ``exoctk`` supports.  First, one should ensure that their version of ``conda`` is up to date:

::

  conda update conda


Next, one should activate the ``base`` environment:

::

  source activate base

Next, one can create the ``exoctk`` ``conda`` environment via the ``environment-3.6.yml`` file:
(Both 3.6 and 3.7 are supported environments, but for our demo we encourage you
to use 3.6.) 

::

  conda env create -f environment-3.6.yml


Lastly, one can activate the newly-created environment and install the exoctk
package with:

::

  source activate exoctk-3.6
  cd exoctk
  python setup.py [install|devlop]


As a final test, cd into your home directory, open up a quick connection to the
Python interpreter, and test that you can import ``exoctk``:

::

    cd
    python
    >>> import exoctk
