
Parameters
=====

Model File Parameters
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
  

Model Specification Parameters
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

**start_date**
    - **Prompt:** Start Time for Simulation (yyyy-mm-ddThh:mm:ss)
    - **Default:** None

**stop_date**
    - **Prompt:** Stop Time for Simulation (yyyy-mm-ddThh:mm:ss)
    - **Default:** None

**segment**
    - **Prompt:** Segmentation, Model Time per Job (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** For a job every model day 1,0,0,0

**LABEL**
    - **Prompt:** Run Label
    - **Default:** None
    - **Description:** A text used to label this model run. It is written to output history files as a global file attribute. This parameter is purely a user convenience, and does not effect the model run in any way.

**START_YEAR**
    - **Prompt:** Model Start Year
    - **Default:** None
    - **Description:** The year for this model run.

**START_DAY**
    - **Prompt:** Start Day
    - **Default:** None
    - **Description:** The starting day of year for this model run.

**SOURCE**
    - **Prompt:** Data File for Startup
    - **Default:** None
    - **Description:** The location of the startup file. It must be a TIEGCM history with the same grid resolution as the model being run. It does not need to be from the same model version as that being run.

**SOURCE_START**
    - **Prompt:** Selected Model Time in Source File
    - **Default:** None
    - **Description:** The selected model time (mtime) in the startup file. This option is typically used to specify the desired time stamp when there are multiple time stamps in one source file. If the SOURCE_START history is not found on the SOURCE file, the model will print an error message and stop.

**PRISTART**
    - **Prompt:** Primary start date (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** The starting model time (Day of year, Hour, Minute, Second) of this model run. The starting time always generates a primary history record. If start_date is given, this will be automatically populated from start_date.

**PRISTOP**
    - **Prompt:** Primary stop date (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** The stopping model time (Day of year, Hour, Minute, Second) of this model run. The stopping time always generates a primary history record. If stop_date is given, this will be automatically populated from stop_date.

**PRIHIST**
    - **Prompt:** Primary History Output Frequency (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** Model time indicating how long the model generates of two primary history records.

**MXHIST_PRIM**
    - **Prompt:** Max Primary History per Output
    - **Default:** None
    - **Description:** The maximum number of records in one primary history file. When this amount of histories have been written to the current OUTPUT file, the next OUTPUT file is created and it receives subsequent histories. This parameter can be adjusted to control the size of primary output files.

**OUTPUT**
    - **Prompt:** Primary Output
    - **Default:** None
    - **Description:** The filenames of primary history files. Multiple files are supported.

**SECSTART**
    - **Prompt:** Start Time for Secondary History Output (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** The starting model time (Day of year, Hour, Minute, Second) to generate the first secondary history record. If start_date is given, this will be automatically populated from start_date.

**SECSTOP**
    - **Prompt:** Stop Time for Secondary History Output (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** The stopping model time (Day of year, Hour, Minute, Second) to generate the last secondary history record. If stop_date is given, this will be automatically populated from stop_date.

**SECHIST**
    - **Prompt:** Secondary History Output Frequency (Day,Hour,Min,Sec)
    - **Default:** None
    - **Description:** Model time indicating how long the model generates of two secondary history records.

**MXHIST_SECH**
    - **Prompt:** Max Secondary History per Output
    - **Default:** None
    - **Description:** The maximum number of records in one secondary history file. When this amount of histories have been written to the current SECOUT file, the next SECOUT file is created and it receives subsequent histories. This parameter can be adjusted to control the size of secondary output files.

**SECOUT**
    - **Prompt:** Secondary Output
    - **Default:** None
    - **Description:** The filenames of secondary history files. Multiple files are supported.

**SECFLDS**
    - **Prompt:** Secondary Output Fields
    - **Default:** ["TN", "UN", "VN", "NE", "TEC", "POTEN", "Z", "ZG"]
    - **Description:** Names of history fields to be outputted. These may be either fields that are also saved on primary histories (so-called "prognostic" fields), fields that have been requested via addfld calls in the source code, or fields available via the diagnostics module.

**STEP**
    - **Prompt:** Model Time Step in Seconds
    - **Default:** None
    - **Description:** The time step of the model in seconds. Default value is 60 seconds for 5-degree resolution, 30 seconds for 2.5-degree resolution, 10 seconds for 1.25-degree resolution, and 5 seconds for 0.625-degree resolution. During periods of quiet solar activity, the model can often be run at larger time steps. During periods of intense solar activity, the model may become numerically unstable. In this case, reducing the time step may be necessary for the model get through the rough period.

**NSTEP_SUB**
    - **Prompt:** Number of O+ Sub-Cycling per Time Step
    - **Default:** 10
    - **Description:** The number of iterations in one model time step for the O+ solver, the actual O+ time step is STEP/NSTEP_SUB.

**POTENTIAL_MODEL**
    - **Prompt:** High-Latitude Potential Model
    - **Default:** "HEELIS"
    - **Valid Options:** ["HEELIS", "WEIMER"]
    - **Description:** The high-latitude potential model used to calculate electric potential above a specified latitude. It can be either Heelis or Weimer.

**GPI_NCFILE**
    - **Prompt:** GPI Data File
    - **Default:** None
    - **Description:** The location of the GPI file containing 3-hourly KP and daily F107, F107A to drive high-latitude convection and the auroral precipitation oval.
    - **Warning:** If GPI_NCFILE is specified, then KP and POWER/CTPOTEN are skipped. If further POTENTIAL_MODEL is WEIMER and IMF_NCFILE is specified, then the Weimer model and aurora will be driven by the IMF data, and only F107 and F107A will be read from the GPI data file.

**IMF_NCFILE**
    - **Prompt:** IMF Data File
    - **Default:** None
    - **Description:** The location of the IMF file containing hourly BXIMF, BYIMF, BZIMF, SWDEN, SWVEL. The data will be used to drive the Weimer 2005 potential model.
    - **Warning:** This can be set only if POTENTIAL_MODEL is WEIMER. If IMF file is specified BXIMF, BYIMF, BZIMF, SWDEN, and SWVEL are skipped. If the current model time is not available on the IMF data file, the model will print an error message and stop.

**KP**
    - **Prompt:** Geomagnetic Activity Index
    - **Default:** None
    - **Warning:** If KP is specified and POWER and/or CTPOTEN are skipped, then the given KP will be used to calculate POWER and/or CTPOTEN using empirical formulas, which are used in auroral parameterization and Heelis model.

**POWER**
    - **Prompt:** Hemispheric Power
    - **Default:** None
    - **Description:** Used in auroral parameterization and Heelis model.

**CTPOTEN**
    - **Prompt:** Cross-Tail Potential
    - **Default:** None
    - **Description:** Used in the auroral parameterization and Heelis model.
    - **Warning:** If POTENTIAL_MODEL is WEIMER, then the user is not allowed to provide CTPOTEN because it will be calculated from the Weimer electric potential.

**BXIMF**
    - **Prompt:** Interplanetary Magnetic Field Bx in nT
    - **Default:** None
    - **Warning:** Only used if POTENTIAL_MODEL is WEIMER

**BYIMF**
    - **Prompt:** Interplanetary Magnetic Field By in nT
    - **Default:** None
    - **Warning:** Only used if POTENTIAL_MODEL is WEIMER

**BZIMF**
    - **Prompt:** Interplanetary Magnetic Field Bz in nT
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
    - **Prompt:** Daily F10.7
    - **Default:** None
    - **Description:** Daily 10.7 cm solar flux.

**F107A**
    - **Prompt:** 81-Day Average of F10.7
    - **Default:** None
    - **Description:** 81-day averaged 10.7 cm solar flux.

INTERMEDIATE Parameters
""""""""""""""""""""

**AMIENH,AMIESH**
    - **Prompt:** AMIE Northern and Southern Hemisphere Data
    - **Default:** None
    - **Description:** Data files containing output from the AMIE model to be imported into TIEGCM. AMIENH is northern hemisphere, AMIESH is southern hemisphere. Contact Gang Lu (ganglu@ucar.edu) for more information.

**BGRDDATA_NCFILE**
    - **Prompt:** Data File for Zonal Mean Climatology of T, U, V, Z
    - **Default:** None
    - **Description:** Data file providing zonal mean climatology of T, U, V, and Z coming from either empirical models (e.g., MSIS, HWM) or reanalysis data (e.g., NOGAPS-ALPHA). If no input file is specified, a flat lower boundary (U = V = 0, T = 181K, Z = 96.4km) is employed by default.

**GSWM_MI_DI_NCFILE**
    - **Prompt:** Data File for Migrating Diurnal Tidal Perturbation of T, U, V, Z from GSWM
    - **Default:** None
    - **Description:** The location of Global Scale Wave Model files containing migrating diurnal tidal perturbations.

**GSWM_MI_SDI_NCFILE**
    - **Prompt:** Data File for Migrating Semi-Diurnal Tidal Perturbation of T, U, V, Z from GSWM
    - **Default:** None
    - **Description:** The location of Global Scale Wave Model files containing migrating semidiurnal tidal perturbations.

**GSWM_NM_DI_NCFILE**
    - **Prompt:** Data File for Non-Migrating Diurnal Tidal Perturbation of T, U, V, Z from GSWM
    - **Default:** None
    - **Description:** The location of Global Scale Wave Model files containing nonmigrating diurnal tidal perturbations.

**GSWM_NM_SDI_NCFILE**
    - **Prompt:** Data File for Non-Migrating Semi-Diurnal Tidal Perturbation of T, U, V, Z from GSWM
    - **Default:** None
    - **Description:** The location of Global Scale Wave Model files containing nonmigrating semidiurnal tidal perturbations.

**CTMT_NCFILE**
    - **Prompt:** Data File for Tidal Perturbation of T, U, V, Z from CTMT
    - **Default:** None
    - **Description:** The location of Climatological Tidal Model of the Thermosphere files containing all tidal perturbations.

EXPERT Parameters
""""""""""""""""""""

**CALENDAR_ADVANCE**
    - **Prompt:** Flag Controling Whether the Model Date Changes Across One Day
    - **Default:** 1
    - **Valid Options:** [0, 1]
    - **Description:** If CALENDAR_ADVANCE is 1, then the calendar time is advanced from START_DAY, iday (init_module) is incremented every 24 hours, and the sun's declination and longitude is recalculated (see sub advance_day in advance.F and sub sunloc in magfield.F), thereby allowing seasonal change to take place. The earth's orbital eccentricity "sfeps" is also updated as a 6% variation in solar output over a year. If 0, the model date doesn't change and is referred to as a "steady-state" run. This is often used to advance the model to a "steady-state" for a given date, prior to a production run with CALENDAR_ADVANCE=1.

**TIDE,TIDE2**
    - **Prompt:** Hough Mode Amplitudes and Phases of Semi-Diurnal/Diurnal Tides
    - **Default:** None
    - **Warning:** TIDE and TIDE2 should be specified only for experiments where amplitude and phases of the tides must be used.

**AURORA**
    - **Prompt:** Flag for Auroral Parameterization
    - **Default:** 1
    - **Valid Options:** [0, 1]
    - **Description:** If AURORA is 1, use Roble & Ridley (1987) auroral model; if 0, no auroral model is applied.

**DYNAMO**
    - **Prompt:** Flag for Electrodynamo Calculation
    - **Default:** 1
    - **Valid Options:** [0, 1]
    - **Description:** If DYNAMO is 1, then dynamo (pdynamo.F) will be called, and ion drift velocities will be calculated. If 0, then dynamo will not be called, and ion drift velocities will be zero.

**CALC_HELIUM**
    - **Prompt:** Flag for Helium Calculation
    - **Default:** 1
    - **Valid Options:** [0, 1]
    - **Description:** If CALC_HELIUM is 1, Helium is calculated as a major composition species. If 0, Helium is zeroed out. If CALC_HELIUM is 1 and the source history does not have Helium, then Helium will be initialized globally to 0.1154E-5.

**EDDY_DIF**
    - **Prompt:** Flag for Day-of-Year Dependent Eddy Diffusion Coefficient
    - **Default:** 0
    - **Valid Options:** [0, 1]
    - **Description:** If EDDY_DIF is 1, then day-of-year dependent eddy diffusion will be calculated, otherwise eddy diffusion will be set to pressure-dependent constants. See cons.F.

**JOULEFAC**
    - **Prompt:** Joule Heating Factor
    - **Default:** 1.5
    - **Description:** This factor is multiplied by the joule heating calculation (see subroutine qjoule_tn in qjoule.F).

**COLFAC**
    - **Prompt:** O-O+ Collision Frequency Factor
    - **Default:** 1.5
    - **Description:** O-O+ collision frequency, alias the "Burnside Factor". Default is 1.5, but there have been recommendations for 1.3. COLFAC is used in lamdas.F and oplus.F.

**ELECTRON_HEATING**
    - **Prompt:** Thermal Electron Heating Scheme
    - **Default:** 6
    - **Valid Options:** [4, 6]
    - **Description:** 4 for the 4th order scheme (Swartz & Nisbet 1972) and 6 for the 6th order scheme (Smithtro & Solomon 2008).

**HE_COEFS_NCFILE**
    - **Prompt:** Data File for Helium Coefficients
    - **Default:** None
    - **Description:** The location of Helium coefficient data file used for Helium upper boundary flux calculation.

**SABER_NCFILE**
    - **Prompt:** Data File for Tidal Perturbation of T, Z from SABER
    - **Default:** None
    - **Description:** The location of SABER files containing tidal perturbations of temperature and geopotential height.

**TIDI_NCFILE**
    - **Prompt:** Data File for Tidal Perturbation of U, V from TIDI
    - **Default:** None
    - **Description:** The location of TIDI files containing tidal perturbations of zonal and meridional neutral winds.

**OPDIFFCAP**
    - **Prompt:** Maximum O+ Ambipolar Diffusion coefficient
    - **Default:** 0
    - **Description:** Optional cap on ambipolar diffusion coefficient for O+. This can improve model stability in the topside F-region, but it is only recommended as a last resort since it will change model results. The default is 0, i.e., no cap. If this is non-zero (provided by the user), then it is implemented in subroutine rrk of src/oplus.F.

**CURRENT_PG**
    - **Prompt:** Flag for Pressure Gradient and Gravity Force in Electrodynamo
    - **Default:** 1
    - **Valid Options:** [0, 1]
    - **Description:** If CURRENT_PG is 1, current due to plasma pressure gradient and gravity is calculated and included as a forcing term in the dynamo equation (ignored if DYNAMO is 0).

**CURRENT_KQ**
    - **Prompt:** Flag for Current Sheet Calculation in Electrodynamo
    - **Default:** 0
    - **Valid Options:** [0, 1]
    - **Description:** If CURRENT_KQ is 1, then height-integrated current density of current sheet, and upward current density at the top of the ionosphere is calculated (ignored if DYNAMO is 0). See current.F90 to save JQR, JE13D, JE23D, KQPHI, KQLAM.

**DOECLIPSE**
    - **Prompt:** Flag for Eclipse Mask
    - **Default:** false
    - **Valid Options:** [true, false]
    - **Description:** Apply an Eclipse mask if an eclipse occurs during this event. Will do nothing if there are no eclipses during this event. Applies partial, annular, or total solar eclipse masks.

**ONEWAY**
    - **Prompt:** Enable One-way Coupling To Remix
    - **Default:** false
    - **Valid Options:** [true, false]
    - **Description:** Enable one-way coupling from remix to TIEGCM. Read remix h5 file. Must be named or linked as msphere.mix.h5.
    - **Warning:** HEELIS must be set for One-way Coupling

**other_input**
    - **Prompt:** Other input parameters
    - **Default:** [null]
    - **Warning:** Advanced usage only. Intended for users with a deep understanding of TIEGCM configurations and requirements.



PBS Job Parameters
----------------------------

This document details the configuration for PBS job parameters required for running the model on Derecho and Pleiades supercomputers. Parameters are organized by the system and user expertise levels: Basic, Intermediate, and Expert.

Derecho System Parameters
""""""""""""""""""""

Basic Parameters
""""""""""

**Project Code**
    - **Prompt:** Project Code
    - **Default:** P28100036
    - **Description:** Identifier for the project under which the job is submitted.

**Requested Wall Time**
    - **Prompt:** WARNING: You are responsible for ensuring that the wall time is sufficient to run a segment of your simulation! Requested wall time for each PBS job segment (HH:MM:SS)
    - **Default:** 12:00:00
    - **Warning:** Maximum walltime is 12:00:00.

Intermediate Parameters
""""""""""

**PBS Queue Name**
    - **Prompt:** PBS queue name
    - **Default:** main
    - **Valid Options:** [develop, main, preempt]
    - **Description:** The queue in which the job will be submitted.

**PBS Job Priority**
    - **Prompt:** PBS job priority
    - **Default:** regular
    - **Valid Options:** [premium, regular, economy, preempt]

Expert Parameters
""""""""""

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

Pleiades System Parameters
""""""""""""""""""""

Basic Parameters
""""""""""

**PBS Queue Name**
    - **Prompt:** PBS queue name
    - **Default:** normal
    - **Valid Options:** [low, normal, long, debug, devel]
    - **Description:** The queue in which the job will be submitted on Pleiades.

**Requested Wall Time**
    - **Prompt:** WARNING: You are responsible for ensuring that the wall time is sufficient to run a segment of your simulation! Requested wall time for each PBS job segment (HH:MM:SS)
    - **Default:** 12:00:00
    - **Warning:** Maximum walltime on normal queue is 12:00:00.

Expert Parameters
""""""""""

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