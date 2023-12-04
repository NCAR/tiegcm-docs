Usage
=====

tiegcmpy can be run in two modes:

API Mode
--------

For use in custom Python scripts or Jupyter notebooks.

.. code-block:: python

    import tiegcmpy as ty

### Importing tiegcmpy

.. code-block:: python

    import tiegcmpy as ty

### Loading Datasets

#### Loading a single dataset

.. code-block:: python

    ty.load_dataset(directory, dataset_filter)

#### Loading multiple datasets

.. code-block:: python

    ty.load_datasets(directory, dataset_filter)

### Plot Generation

The following plots can be made:

- Latitude vs Longitude plots: plt_lat_lon
- Pressure level vs Variable Value plots: plt_lev_var
- Pressure level vs Longitude plots: plt_lev_lon
- Pressure level vs Latitude plots: plt_lev_lat
- Pressure level vs Time plots: plt_lev_time
- Latitude vs Time plots: plt_lat_time

.. note::

    Look at the functionality section for a list of all plot types with required and optional arguments.

Command Line Interface (CLI) Mode
---------------------------------

For a command line interface with arguments.

### Single Plot

Example command for generating a single plot:

.. code-block:: bash

    tiegcmpy --plot_type {plot_type} -dir {directory of datasets} --dataset_filter {primary or secondary files} --output_format {format of output plot} --[Other optional arguments for specific plots]

### Multiple Plots

There are several options for generating multiple plots:

#### Option 1: Interactive Mode

.. code-block:: bash

    tiegcmpy -rec

Follow the instructions on the screen to enter the command mode.

#### Option 2: Load dataset for multiple plot generation to multiple files

.. code-block:: bash

    tiegcmpy -rec -dir {directory of datasets} --dataset_filter {primary or secondary files}

#### Option 3: Load dataset for multiple plot generation to a single PDF file

.. code-block:: bash

    tiegcmpy -rec -dir {directory of datasets} --dataset_filter {primary or secondary files} --multiple_output {Output PDF file name}