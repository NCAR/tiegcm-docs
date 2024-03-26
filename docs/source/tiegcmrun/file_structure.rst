File Structure
==============

The tiegcmrun script dependencies is structured as follows:

.. code-block:: none

    ├── options_description.json    # Manages default values and expertise levels for variables  
    ├── benchmarks.json             # Contains benchmark-specific variables     
    ├── template.inp                # Jinja2 template for input files
    ├── template.pbs                # Jinja2 template for PBS files   
    └── tiegcmrun.py                # The main script for running TIEGCM simulations