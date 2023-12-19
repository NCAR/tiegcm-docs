Usage
=====

tiegcmpy can be run in two modes: API and Command Line Interface (CLI).

Mode: API
---------

tiegcmpy can be used in custom Python scripts or Jupyter notebooks.

**Importing tiegcmpy**

.. code-block:: python

    import tiegcmpy as ty

**Loading Datasets**

Loading a dataset/datasets:

  .. note::

      For the inbuilt plotting routines only this method can be used to load the NetCDF datasets.


  .. code-block:: python

      ty.load_datasets(directory/file, dataset_filter)


**Plot Generation**

The following plots can be made with tiegcmpy:

- Latitude vs Longitude plots
- Pressure level vs Variable Value plots
- Pressure level vs Longitude plots
- Pressure level vs Latitude plots
- Pressure level vs Time plots
- Latitude vs Time plots

Examples and detailed usage can be found in the Functionality section.

Mode: CLI (Command Line Interface)
----------------------------------

tiegcmpy can also be used directly from the command line.

**Single Plot**

Example:

.. code-block:: bash

    tiegcmpy --plot_type {plot_type} -dir {directory of datasets} --dataset_filter {primary or secondary files} --output_format {format of output plot} --[Other optional arguments for specific plots]

**Multiple Plots**

Multiple plots can be generated from different datasets using tiegcmpy's CLI. Here are some examples:

1. **Interactive Mode for Multiple Plots**

   In this mode, tiegcmpy prompts the user to select datasets and plot types interactively.

   .. code-block:: bash

       tiegcmpy --interactive

   Follow the on-screen prompts to select datasets and specify plot types.

2. **Multiple Plot Generation to Multiple Files**

   This mode allows for the generation of different plots from a single dataset, each saved to a separate file.

   .. code-block:: bash

       tiegcmpy --plot_types "lat_lon,lev_var" --dir "/path/to/datasets" --output_format "png" --output_dir "/path/to/output"

   This command generates latitude vs longitude and level vs variable plots for each dataset in the specified directory.

3. **Multiple Plot Generation to a Single PDF File**

   Generate multiple plots from a dataset and compile them into a single PDF file.

   .. code-block:: bash

       tiegcmpy --plot_types "lat_lon,lev_var" --dir "/path/to/datasets" --output_format "pdf" --output_file "combined_plots.pdf"

   This command generates multiple plots and compiles them into 'combined_plots.pdf'.