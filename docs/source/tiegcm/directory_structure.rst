Directory Structure
=======================

To successfully run the model, you must define several directory paths in the job script. These paths, which can be absolute or relative to the working directory, include:

- **workdir**: A user-created directory from where model runs are initiated.
- **modeldir**: Contains the model source code, possibly a SVN working copy.
- **tgcmdata**: Stores start-up history and input data files.
- **execdir**: The directory where the model is built and executed.

Example configurations in the job script might look like:

.. code-block:: none

   set modeldir = tiegcm_trunk
   set tgcmdata = /my/prettybig/data/tiegcm.data
   set execdir = /my/big/exec/disk/tiegcm.exec

Working Directory
-------------------
The initial setup for a user's working directory typically includes:

.. code-block:: none

                 workdir
                    |
    -----------------------------------------------
                 |                    |
               *.inp              modeldir/
               *.job
               *.out

Files involved are:

- **\*.inp**: Namelist input files
- **\*.job**: Job scripts
- **\*.out**: STDOUT output files from model runs, validated by the input module (input.F)

The job script locates the modeldir and other necessary scripts. It also uses the TGCMDATA environment variable, or an override variable from the script, to locate necessary data files.

Model Directory
-------------------

The model directory structure is laid out as follows:

.. code-block:: none

                 modeldir
                    |
    ---------------------------------------------------------
       |              |              |             |         |
      src/         scripts/        doc/        tgcmrun/   benchmarks/
       |              |              |             |         |
      *.F90         Make.*       userguide/       *.py    run_climatology
      *.F         linux.job     description/     run_*     run_seasons
      *.h          ibm.job        release/     tgcmrun     run_storms
                 default.inp     diags.table                archive_hpss
                tgcm_contents   perf.table                 make_listings
                 tgcm_ncdump   README.download             postproc/
                    etc

Each subdirectory contains specific types of files crucial for model setup, execution, and testing. 

Data Directory
-------------------

Outlined below are the contents of the data directory which holds netCDF files necessary for running the current model version.

.. code-block:: none

                  datadir for tiegcmx.x
                          |
    ----------------------------------------------
                          |
                tiegcmx.x_res5.0_*.nc
                tiegcmx.x_res2.5_*.nc
                        gpi*.nc
                      gswm*5.0d*.nc
                      gswm*2.5d*.nc
                      imf_OMNI_*.nc
                         etc

These files include various model configurations and inputs, and the specifics for each file type are detailed in the namelist input files.
