Quickstart
=====

The TIEGCM tool, tiegcmrun, offers a flexible command-line interface for running TIE-GCM simulations. This document outlines the various commands and options available to users, enabling them to execute simulations, compile the model, and customize runs according to their requirements.

Running Simulations
-------------------

Tiegcmrun provides several options for running simulations, compiling the model, and debugging. Below is a detailed description of the available options:

.. code-block:: bash

    -h, --help               Show this help message and exit.
    -e, --execute            Submit TIEGCM job (default: False).
    -c, --compile            Compile TIEGCM (default: False).
    -oc, --onlycompile       Compile and skip other TIEGCM processes (default: False).
    -d, --debug              Print debugging output (default: False).
    --mode MODE              User mode (BENCH|BASIC|INTERMEDIATE|EXPERT) (default: BASIC).
    -co, --coupling          Enable coupling (default: False).
    -o OPTIONS_PATH, --options_path OPTIONS_PATH
                             Path to JSON file of options (default: None).
    -v, --verbose            Print verbose output (default: False).
    -bench BENCHMARK, --benchmark BENCHMARK
                             Benchmark run name (default: None).

These options allow users to tailor the simulation process to their needs, whether they are running standard benchmarks, requiring detailed debugging information, or conducting a custom simulation.


Usage
--------------

Prerequisites
""""""""""""""""

Setup the environment by following the `Environment Setup <https://tiegcm-docs.readthedocs.io/en/latest/tiegcm/environment_setup.html>`_ page.

Regular Run
""""""""""

For custom simulations, you can move to the desired directory and simply run tiegcmrun without specifying a benchmark:

.. code-block:: bash

    python $TIEGCMHOME/tiegcmrun/tiegcmrun.py -c -e

-c/--compile is to compile
-e/--execute is to submit the Model run as a pbs job

Benchmark Run
""""""""""

Tiegcmrun supports a variety of predefined benchmark runs, catering to different scientific interests and scenarios. Below are the supported benchmark runs:

**Seasons:**

- decsol_smax
- decsol_smin
- junsol_smax
- junsol_smin
- mareqx_smax
- mareqx_smin
- sepeqx_smax
- sepeqx_smin

**Storms:**

- dec2006_heelis_gpi
- dec2006_weimer_imf
- jul2000_heelis_gpi
- jul2000_weimer_imf
- nov2003_heelis_gpi
- nov2003_weimer_imf
- whi2008_heelis_gpi
- whi2008_weimer_imf

**Climatology:**

- climatology_smax
- climatology_smin


Benchmark runs are predefined simulations that allow users to test and compare the performance and output of TIE-GCM. To execute a benchmark run, move to the directory where you wish to have the run and use the following command:

.. code-block:: bash

    python $TIEGCMHOME/tiegcmrun/tiegcmrun.py -bench {benchmark_name} -c -e

Where `{benchmark_name}` is the name of the benchmark you wish to run. Tiegcmrun supports several benchmark scenarios, including different seasons and storm events.


Reruns and Modifications
""""""""""

To rerun a previous simulation, possibly with some modifications, you can use the same commands as for custom runs. If you have a specific configuration or set of options saved from a previous run, you can specify this using the `--options_path` flag.

.. code-block:: bash

    python $TIEGCMHOME/tiegcmrun/tiegcmrun.py --options_path {path_to_options.json}

This allows for a high degree of customization, enabling users to simulate specific scenarios tailored to their research needs.


Subdirectories Created by Tiegcmrun
-----------------------------------

After running a simulation, tiegcmrun creates several subdirectories to organize the output:

- `/exec`: Contains all the compilation output files.
- `/hist`: Contains all the TIE-GCM output NetCDF files (Primary and Secondary).
- `/stdout`: Contains the TIEGCM input file (.inp), PBS file (.pbs), JSON file (.json), log file (.out), and the executable (.exe/.o).

This structured output makes it easier for users to find and analyze the results of their simulations.

By following these guidelines, users can effectively leverage tiegcmrun for a wide range of simulations, from simple benchmark runs to complex, custom scenarios tailored to their specific research questions.
