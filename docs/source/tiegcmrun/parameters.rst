
Parameters
=====

Model Files
----------------

This outlines the configuration for various directories and files required for running the model. These configurations are categorized based on user expertise levels: Basic, Intermediate, and Expert.

Basic Parameters
""""""""""""""""""""

These parameters are crucial for setting up the model's environment, including specifying directories and key files.

**Directory of model**
    - **Prompt:** Directory of model
    - **Default:** None
    - **Description:** The root directory where `src/` and `scripts/` are located.

**Root directory for all files for execution**
    - **Prompt:** Root directory for all files for execution
    - **Default:** None
    - **Description:** The parent directory where all the run files/subdirectories will be located.

**Directory of Tiegcm Data Files**
    - **Prompt:** Directory of Tiegcm Data Files
    - **Default:** None
    - **Description:** The directory where some required input data for the model are located.

**Custom Input File / ENTER to build INP file**
    - **Prompt:** Custom Input File / ENTER to build INP file
    - **Default:** None
    - **Description:** A text file listing input parameters for the model.

**Executable**
    - **Prompt:** Executable
    - **Default:** None
    - **Description:** The path of existing or name of the executable to be used for the model run.

Intermediate Parameters
""""""""""""""""""""

Intermediate parameters provide additional detail for users familiar with model setup, allowing finer control over execution and output.

**Execution Directory**
    - **Prompt:** Execution Directory
    - **Default:** `os.getcwd()`
    - **Description:** The directory where the executable will be located and the model will be run.

**Working Directory**
    - **Prompt:** Working Directory
    - **Default:** `os.getcwd()`
    - **Description:** The directory where input files will be located.

**Output Directory**
    - **Prompt:** Output Directory
    - **Default:** `os.getcwd()`
    - **Description:** The directory where output files will be located.

**Log File**
    - **Prompt:** Log File
    - **Default:** None
    - **Description:** A text file which is generated during a model run with diagnostic information of the model.

Expert Parameters
""""""""""""""""""""

Expert-level parameters are intended for advanced users who require detailed control over the model setup and build process.

**Make File**
    - **Prompt:** Make File
    - **Default:** None
    - **Description:** A text file used for building the model.
    - **Warning:** Modify only if you are porting the model to a new machine.
  

Model Specifications
----------------

This delineates the model specifications segregated by user expertise levels: Bench/Basic (for all users), Intermediate, and Expert. These specifications are crucial for setting up the model's spatial configuration and determining its resolution and coverage.

BASIC Parameters
""""""""""""""""""""

These parameters are essential for basic model setup and are suitable for all users, including those with less experience in model configuration.

**Horizontal Resolution**
    - **Level:** BENCH
    - **Prompt:** Horizontal Resolution (Deg)
    - **Default:** 2.5
    - **Valid Options:** [2.5, 1.25, 0.625]
    - **Description:** Defines the longitudinal and latitudinal spacing of the model grid, influencing the model's geographical detail and computational demands.

**Vertical Resolution**
    - **Level:** BENCH
    - **Prompt:** Vertical Resolution (Scale Height)
    - **Default:** 0.25
    - **Valid Options:** [0.25, 0.125, 0.0625]
    - **Description:** Specifies the vertical grid spacing, crucial for accurate atmospheric layer representation.

**Magnetic Grid Resolution**
    - **Level:** BENCH
    - **Prompt:** Magnetic grid resolution (Degree)
    - **Default:** 2
    - **Valid Options:** [2, 1, 0.5]
    - **Description:** Sets the spacing for the magnetic latitudinal grid at high latitudes, important for studies focusing on auroral and polar phenomena.

Intermediate Parameters
""""""""""""""""""""

These parameters provide additional detail for users with some experience in model setup, allowing for finer control over the simulation environment.

**Highest Pressure Level**
    - **Level:** INTERMEDIATE
    - **Prompt:** Highest pressure level
    - **Default:** 7
    - **Valid Options:** [7, 8, 9, 10, 11]
    - **Description:** Determines the topmost pressure level in the model, affecting the vertical extent of the simulated atmosphere.

Expert Parameters
""""""""""""""""""""

Expert-level parameters are intended for advanced users who require detailed control over the model setup. These settings should be adjusted with caution.

**nres_grid**
    - **Level:** EXPERT
    - **Prompt:** nres_grid
    - **Default:** None
    - **Warning:** Automatically populated. Do not change.
    - **Description:** An advanced configuration parameter that is automatically determined based on other settings. Manual adjustment is not recommended, as it can impact the model's performance and results.

By carefully selecting these parameters, users can tailor the model to specific scientific needs, balancing detail against computational requirements. Adjustments to resolution and grid settings can significantly influence simulation outcomes, making it essential to choose these values thoughtfully.


Input File Parameters
----------------

The input file for TIEGCM simulations contains several parameters that control various aspects of the simulation. Below is a detailed description of these parameters, categorized by their level of expertise required: BASIC, INTERMEDIATE, and EXPERT.

BASIC Parameters
""""""""""""""""""""

**LABEL**
    - **Prompt:** Run Label
    - **Default:** None
    - **Description:** A text used to label this model run.

**start_date**
    - **Prompt:** Start date for simulation (yyyy-mm-ddThh:mm:ss)
    - **Default:** None

**stop_date**
    - **Prompt:** Stop date for simulation (yyyy-mm-ddThh:mm:ss)
    - **Default:** None

**SOURCE**
    - **Prompt:** SOURCE file location
    - **Default:** None
    - **Description:** The location of the startup file.

**segment**
    - **Prompt:** Segmentation, Model time per job (Day,Hour,Minute,Second)
    - **Default:** None
    - **Description:** For a job every model day 1,0,0,0

**START_DAY**
    - **Prompt:** Start Day
    - **Default:** None
    - **Description:** The starting day of year for this model run.

**PRIHIST**
    - **Prompt:** Primary History (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** Model time indicating how long the model generates of two primary history records.

**MXHIST_PRIM**
    - **Prompt:** Max Primary History per Output
    - **Default:** None
    - **Description:** The maximum number of records in one primary history file.

**OUTPUT**
    - **Prompt:** Primary Output
    - **Default:** None
    - **Description:** The filenames of primary history files. Multiple files are supported.

**SECHIST**
    - **Prompt:** Secondary History (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** Model time indicating how long the model generates of two secondary history records.

**MXHIST_SECH**
    - **Prompt:** Max Secondary History per Output
    - **Default:** None
    - **Description:** The maximum number of records in one secondary history file.

**SECOUT**
    - **Prompt:** Secondary Output
    - **Default:** None
    - **Description:** The filenames of secondary history files. Multiple files are supported.

**SECFLDS**
    - **Prompt:** Secondary Output Fields
    - **Default:** ["TN","UN","VN","NE","TEC","POTEN","Z","ZG"]
    - **Description:** Names of history fields to be outputted.

**POTENTIAL_MODEL**
    - **Prompt:** High-latitude potential model that is going to be used
    - **Default:** "HEELIS"
    - **Valid Options:** ["HEELIS", "WEIMER"]
    - **Description:** High-latitude potential model that is going to be used: Heelis/Weimer.

**GPI_NCFILE**
    - **Prompt:** GPI file
    - **Default:** None
    - **Description:** The location of the GPI file containing 3-hourly KP and daily F107, F107A.
    - **Warning:** If GPI file is specified KP and POWER/CTPOTEN are skipped.

**IMF_NCFILE**
    - **Prompt:** IMF file
    - **Default:** None
    - **Description:** The location of the IMF file containing hourly BXIMF, BYIMF, BZIMF, SWDEN, SWVEL.
    - **Warning:** This can be set only if POTENTIAL_MODEL is WEIMER. If IMF file is specified BXIMF, BYIMF, BZIMF, SWDEN, and SWVEL are skipped.

**KP**
    - **Prompt:** Kp index
    - **Default:** None
    - **Description:** If KP is specified and POWER and/or CTPOTEN are skipped, then the given KP will be used with empirical formulas to calculate POWER and/or CTPOTEN, which are used in auroral parameterization and Heelis model.
    - **Warning:** If KP is specified and POWER and/or CTPOTEN are skipped.

**POWER**
    - **Prompt:** POWER
    - **Default:** None
    - **Description:** Used in auroral parameterization and Heelis model.

**CTPOTEN**
    - **Prompt:** CTPOTEN
    - **Default:** None
    - **Description:** Used in the auroralparameterization and Heelis model. Note that if POTENTIAL_MODEL is WEIMER, then the user is not allowed to provide CTPOTEN because it will be calculated from the Weimer electric potential.

**BXIMF**
    - **Prompt:** Inter-Magnetic Field Bx in nT
    - **Default:** None
    - **Warning:** Only used if POTENTIAL_MODEL is WEIMER

**BYIMF**
    - **Prompt:** Inter-Magnetic Field By in nT
    - **Default:** None
    - **Warning:** Only used if POTENTIAL_MODEL is WEIMER

**BZIMF**
    - **Prompt:** Inter-Magnetic Field Bz in nT
    - **Default:** None
    - **Warning:** Only used if POTENTIAL_MODEL is WEIMER

**SWDEN**
    - **Prompt:** Solar Wind Density in cm-3
    - **Default:** None
    - **Warning:** Only used if POTENTIAL_MODEL is WEIMER

**SWVEL**
    - **Prompt:** Solar Wind Velocity in km/s
    - **Default:** None
    - **Warning:** Only used if POTENTIAL_MODEL is WEIMER

**F107**
    - **Prompt:** F10.7
    - **Default:** None
    - **Description:** Daily 10.7 cm solar flux.

**F107A**
    - **Prompt:** 81-Day Average of F10.7
    - **Default:** None
    - **Description:** 81-day averaged 10.7 cm solar flux.

INTERMEDIATE Parameters
""""""""""""""""""""

**SOURCE_START**
    - **Prompt:** Selected Date in Source File
    - **Default:** None
    - **Description:** The selected model time (mtime) in the startup file.

**START_YEAR**
    - **Prompt:** Source Start Year
    - **Default:** None
    - **Description:** The year for this model run.

**STEP**
    - **Prompt:** STEP number
    - **Default:** None
    - **Description:** The time step of the model in seconds.

**SECSTART**
    - **Prompt:** Secondary Start Date (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** The starting model time (Day of year, Hour, Minute, Second) to generate the first secondary history record.

**SECSTOP**
    - **Prompt:** Secondary Stop Date (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** The stopping model time (Day of year, Hour, Minute, Second) to generate the last secondary history record.

**ELECTRON_HEATING**
    - **Prompt:** Thermal Electron Heating Scheme
    - **Default:** 6
    - **Valid Options:** [4, 6]
    - **Description:** 4 for the 4th order scheme (Swartz & Nisbet 1972) and 6 for the 6th order scheme (Smithtro & Solomon 2008).

**DOECLIPSE**
    - **Prompt:** Apply Eclipse Mask
    - **Default:** false
    - **Valid Options:** [true, false]
    - **Description:** Apply an Eclipse mask if an eclipse occurs during this event. Will do nothing if there are no eclipses during this event. Applies partial, annular, or total solar eclipse masks.

**ONEWAY**
    - **Prompt:** Enable One-way Coupling To Remix
    - **Default:** false
    - **Valid Options:** [true, false]
    - **Description:** Enable one-way coupling from remix to TIEGCM. Read remix h5 file. Must be named or linked as msphere.mix.h5.
    - **Warning:** HEELIS must be set for One-way Coupling

EXPERT Parameters
""""""""""""""""""""

**CALENDAR_ADVANCE**
    - **Prompt:** Whether the model date changes across one day
    - **Default:** 1
    - **Description:** 1 for model runs with advancing dates (date changes across a model day). 0 for model runs with constant dates (date doesn’t change across a model day). CALENDAR_ADVANCE=0 is usually used to prepare the startup file for a production run; CALENDAR_ADVANCE=1 is used in a production run.

**PRISTART**
    - **Prompt:** Primary start date (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** The starting model time (Day of year, Hour, Minute, Second) of this model run. The starting time always generates a primary history record.

**PRISTOP**
    - **Prompt:** Primary stop date (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** The stopping model time (Day of year, Hour, Minute, Second) of this model run. The stopping time always generates a primary history record.

**NSTEP_SUB**
    - **Prompt:** NSTEP_SUB number
    - **Default:** "10"
    - **Description:** The number of iterations in one model time step for the O+ solver, the actual O+ time step is STEP/NSTEP_SUB.

**GSWM_MI_DI_NCFILE**
    - **Prompt:** GSWM diurnal migrating data file
    - **Default:** None
    - **Description:** The location of Global Scale Wave Model files containing diurnal migrating tidal perturbations.

**GSWM_MI_SDI_NCFILE**
    - **Prompt:** GSWM semidiurnal migrating data file
    - **Default:** None
    - **Description:** The location of Global Scale Wave Model files containing semidiurnal migrating tidal perturbations.

**GSWM_NM_DI_NCFILE**
    - **Prompt:** GSWM diurnal nonmigrating data file
    - **Default:** None
    - **Description:** The location of Global Scale Wave Model files containing diurnal nonmigrating tidal perturbations.

**GSWM_NM_SDI_NCFILE**
    - **Prompt:** GSWM semidiurnal nonmigrating file
    - **Default:** None
    - **Description:** The location of Global Scale Wave Model files containing semidiurnal nonmigrating tidal perturbations.

**HE_COEFS_NCFILE**
    - **Prompt:** HE Coefs file
    - **Default:** None
    - **Description:** The location of HE Coefs file containing coefficients for high efficiency computations.

**other_input**
    - **Prompt:** Other input parameters
    - **Default:** [null]
    - **Warning:** Advanced usage only. Intended for users with a deep understanding of TIEGCM configurations and requirements.



PBS Job Parameters
----------------------------

This document details the configuration for PBS job parameters required for running the model on Derecho and Pleiades supercomputers. Parameters are organized by the system and user expertise levels: Basic, Intermediate, and Expert.

Derecho System Configuration
""""""""""""""""""""

Basic Configuration
''''''''''

**Project Code**
    - **Prompt:** Project Code
    - **Default:** P28100036
    - **Description:** Identifier for the project under which the job is submitted.

**Requested Wall Time**
    - **Prompt:** WARNING: You are responsible for ensuring that the wall time is sufficient to run a segment of your simulation! Requested wall time for each PBS job segment (HH:MM:SS)
    - **Default:** 12:00:00
    - **Warning:** Maximum walltime is 12:00:00.

Intermediate Configuration
''''''''''

**PBS Queue Name**
    - **Prompt:** PBS queue name
    - **Default:** main
    - **Valid Options:** [develop, main, preempt]
    - **Description:** The queue in which the job will be submitted.

**PBS Job Priority**
    - **Prompt:** PBS job priority
    - **Default:** regular
    - **Valid Options:** [premium, regular, economy, preempt]

Expert Configuration
''''''''''

**Select (Number of Nodes)**
    - **Prompt:** Number of nodes to request
    - **Default:** None
    - **Description:** Specifies the total number of nodes allocated for the job. Adjust based on the job's computational requirements.

**NCPUs (Cores per Node)**
    - **Prompt:** Number of cores per node
    - **Default:** None
    - **Description:** Determines the number of CPU cores per node. This should align with the parallelization and performance characteristics of your application.

**MPIProcs (MPI Ranks per Node)**
    - **Prompt:** Number of MPI ranks per node
    - **Default:** None
    - **Description:** Configures the distribution of MPI processes across the allocated nodes. This setting is pivotal for applications with MPI-based parallelization.

**NProcs (Total MPI Processes)**
    - **Prompt:** nprocs (nnodes * mpiprocs)
    - **Default:** None
    - **Description:** Automatically calculated as the product of nodes and MPI processes per node. It represents the total number of MPI processes deployed.

**Saved Module List**
    - **Prompt:** Saved Module List
    - **Description:** Optionally add a saved list or ENTER to add the individual modules.

**Modules to Load**
    - List of modules to be loaded for the job.

**Additional Settings**
    - **Prompt:** Additional settings or env variables
    - **Description:** Any extra PBS directives or environment variables to be set.

Pleiades System Configuration
""""""""""""""""""""

Basic Configuration
''''''''''

**PBS Queue Name**
    - **Prompt:** PBS queue name
    - **Default:** normal
    - **Valid Options:** [low, normal, long, debug, devel]
    - **Description:** The queue in which the job will be submitted on Pleiades.

**Requested Wall Time**
    - **Prompt:** WARNING: You are responsible for ensuring that the wall time is sufficient to run a segment of your simulation! Requested wall time for each PBS job segment (HH:MM:SS)
    - **Default:** 12:00:00
    - **Warning:** Maximum walltime on normal queue is 12:00:00.

Expert Configuration
''''''''''

**Model (System on PFE)**
    - **Prompt:** System on PFE to use
    - **Default:** "bro"
    - **Valid Options:** ["bro", "has", "ivy", "san"]
    - **Description:** Selects the specific hardware architecture within Pleiades to target for the job. Choice affects available resources and performance.

**Select (Number of Nodes)**
    - **Prompt:** Number of nodes to request
    - **Default:** None
    - **Description:** Defines the total number of compute nodes for the job. Essential for scaling and resource allocation.

**NCPUs (Cores per Node)**
    - **Prompt:** Number of cores per node
    - **Default:** None
    - **Description:** Sets the number of cores per node to utilize. Important for jobs requiring high parallelism.

**MPIProcs (MPI Ranks per Node)**
    - **Prompt:** Number of MPI ranks per node
    - **Default:** None
    - **Description:** Specifies the number of MPI ranks per node, defaulting to the number of CPU cores. Adjust according to your application's parallelization needs.

**NProcs (Total MPI Processes)**
    - **Prompt:** nprocs (nnodes * mpiprocs)
    - **Default:** None
    - **Description:** Automatically calculated as the product of nodes and MPI processes per node. It represents the total number of MPI processes deployed.

**Modules to Load**
    - List of modules specific to Pleiades to be loaded for the job.

**Additional Settings**
    - **Prompt:** Additional settings or env variables
    - **Default:** ["setenv MPI_TYPE_DEPTH 32"]
    - **Description:** Any extra directives or environment variables specific to Pleiades.