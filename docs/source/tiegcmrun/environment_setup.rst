
Environment Setup
============

Automatic 
------------

The automatic setup is facilitated through the ``setEnvironment.sh`` script, which simplifies the process of preparing your system for TIEGCM. This script is designed to accommodate users by setting up the environment with minimal input required.

To initiate the setup, execute the following command in your terminal:

.. code-block:: bash

    source {path_to}/setEnvironment.sh

This script performs several functions:

- **System Detection:** Automatically detects the system (currently supports Derecho or Pleiades) and loads the appropriate modules.
- **Modules:** If a saved module list (`SAVED_MODULES`) is provided, it loads this list. Otherwise, it loads a pre-verified list of modules suitable for the detected system. It also prompts the user on whether they wish to save this list for future use.
- **Conda Environment:** For users with an existing Conda environment specified by `CONDA_ENV`, it activates this environment. If not provided, it prompts for the creation of a new Conda environment, which is then created along with the necessary Python dependencies.
- **Environment Variables:** Sets `TIEGCMHOME` and `TIEGCMDATA` environment variables if provided. Otherwise, it will prompt the user to input these values.

The script aims to streamline the setup process, making it more user-friendly by reducing manual steps.

.. warning::

    Environment Variables is currently facing an error with setting `TIEGCMHOME`. Once ``setEnvironment.sh`` is run, set `TIEGCMHOME` environment variable.
    .. code-block:: bash

        export TIEGCMHOME=<<path_to_TIEGCMHOME>>


Manual (NCAR Derecho)
------------
Modules
~~~~~~~~~~~~~~~

For setting up the environment on NCAR systems such as Derecho, you will need to load the following modules:

.. code-block:: bash

    module load ncarenv/23.09
    module load craype/2.7.23
    module load intel/2023.2.1
    module load ncarcompilers/1.0.0
    module load cray-mpich/8.1.27
    module load mkl/2023.2.0
    module load hdf5-mpi/1.12.2
    module load netcdf-mpi/4.9.2
    module load esmf/8.6.0
    module load conda

After loading these modules, you can save this configuration for future use:

.. code-block:: bash

    module save tiegcm

To restore this module list later, simply use:

.. code-block:: bash

    module restore tiegcm

Conda Environment Setup
~~~~~~~~~~~~~~~

After setting up the modules, proceed to create and activate a Conda environment with Python 3.8:

.. note::

   The name of the conda environment in this example is ``tiegcm``.

.. code-block:: bash

    conda create --name tiegcm python=3.8

Activating the environment.

.. note::

   Make sure the conda module is loaded.

.. code-block:: bash

    conda activate tiegcm

Python Package Requirements
----------------------------

Ensure your Conda environment is activated before proceeding. Installation of Tiegcmrun and its dependencies is done via pip, using the `requirements.txt` file located in the Tiegcmrun model directory:

.. code-block:: bash

    pip install -r {path_to_tiegcm_model}/tiegcmrun/requirements.txt

Manual (NASA Pleiades)
------------
Modules
~~~~~~~~~~~~~~~

For setting up the environment on NASA systems such as Pleiades, you will need to load the following modules:

.. code-block:: bash

    module load nas
    module load pkgsrc/2023Q3
    module load comp-intel/2020.4.304
    module load mpi-hpe/mpt.2.28_25Apr23_rhel87
    module load szip/2.1.1
    module load hdf4/4.2.12
    module load hdf5/1.8.18_mpt
    module load netcdf/4.4.1.1_mpt
    module use -a /swbuild/analytix/tools/modulefiles
    module load miniconda3/v4

After loading these modules, you can save this configuration for future use:

.. code-block:: bash

    module save tiegcm

To restore this module list later, simply use:

.. code-block:: bash

    module restore tiegcm

Conda Environment Setup
~~~~~~~~~~~~~~~

After setting up the modules, proceed to create and activate a Conda environment with Python 3.8:

.. note::

    The name of the conda environment in this example is ``tiegcm``.
    .. warning::
        NASA systems such as Pleiades set the custom environment names to ``my_{custom_name}``, in this example its set to ``my_tiegcm``.
        
.. code-block:: bash

    export CONDA_PKGS_DIRS=/nobackup/$USER/.conda/pkgs
    conda create --name tiegcm python=3.8

Activating the environment.

.. note::

   Make sure the conda module is loaded.

.. code-block:: bash

    source activate my_tiegcm

Python Package Requirements
----------------------------

Ensure your Conda environment is activated before proceeding. Installation of Tiegcmrun and its dependencies is done via pip, using the `requirements.txt` file located in the Tiegcmrun model directory:

.. code-block:: bash

    pip install -r {path_to_tiegcm_model}/tiegcmrun/requirements.txt