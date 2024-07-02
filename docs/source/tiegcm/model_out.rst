Model Output History Files
==========================

NetCDF History Output Files
---------------------------

TIEGCM history files are stored in netCDF format, maintained by the UCAR Unidata program, allowing self-describing and platform-independent data organization. The files record the state of model output fields at specific times, making them crucial for data analysis and model continuation.

**Example:** The file *primary.ncd* contains metadata from six days' histories, viewable via the ``ncdump`` utility.

Compliance and File Types
-------------------------

TIEGCM history files adhere to the NetCDF Climate and Forecast (CF) Metadata Convention, ensuring compatibility and standardization:

- **Primary History Files:** These contain essential prognostic fields required to restart the model. Fields like TN, UN, VN, and others are vital for this purpose.
- **Secondary History Files:** These files are used to store diagnostic fields and can include primary fields for detailed temporal analysis, often at a higher frequency than primary files.

Field Data Structure
--------------------

A breakdown of the primary history fields essential for model operations:

.. list-table:: Primary History Fields
   :widths: 20 30 10
   :header-rows: 1

   * - Short Name
     - Long Name
     - Units
   * - TN
     - NEUTRAL TEMPERATURE
     - deg K
   * - UN
     - NEUTRAL ZONAL WIND (+EAST)
     - cm/s
   * - VN
     - NEUTRAL MERIDIONAL WIND (+NORTH)
     - cm/s
   * - O2
     - MOLECULAR OXYGEN
     - mmr
   * - O1
     - ATOMIC OXYGEN
     - mmr
   * - HE
     - HELIUM
     - mmr
   * - OP
     - O+ ION
     - cm-3
   * - N2D
     - N2D
     - mmr
   * - N4S
     - N4S
     - mmr
   * - NO
     - NITRIC OXIDE
     - mmr
   * - AR
     - ARGON (AR)
     - mmr
   * - TI
     - ION TEMPERATURE
     - K
   * - TE
     - ELECTRON TEMPERATURE
     - K
   * - NE
     - ELECTRON DENSITY
     - cm-3
   * - OMEGA
     - VERTICAL MOTION
     - s-1
   * - O2P
     - O2+ ION
     - cm-3
   * - Z
     - GEOPOTENTIAL HEIGHT
     - cm
   * - POTEN
     - ELECTRIC POTENTIAL
     - volts

Fields marked with `_NM` (e.g., TN_NM) are required for the time-stepping scheme, indicating data from the previous timestep necessary for continuity.

