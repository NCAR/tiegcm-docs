Release Notes for TIEGCM 3.0
============================

**Release date**: May 2024  

**Contact**: Discussion group email list tgcmgroup@ucar.edu  

**Download page**: `HAO UCAR TGCM Download <https://github.com/NCAR/tiegcm/tree/master>`_

This is a summary of modifications made to the TIEGCM since the release of TIEGCM 2.0 (March 2016).


Utility Tools
------------

TIEGCMrun
------------

Tiegcmrun is a Python tool (in the tiegcmrun/ directory) that is used to compile and execute tiegcm in an automated fashion. Tiegcmrun can be executed interactively on the command line. See example of usage under `QuickStart <https://tiegcm-docs.readthedocs.io/en/latest/tiegcm/quickstart.html>`_.

TIEGCMpy
------------

Tiegcmpy is a Python tool (`Tiegcmpy github <https://github.com/NCAR/tiegcmpy>`_) that is used for post processing and data visualization of TIEGCM outputs. Tiegcmpy can be executed interactively on the command line or as an API in a python script. See example of usage `TIEGCMpy Docs <https://tiegcmpy.readthedocs.io/>`_.

New Features and Functional Changes
-----------------------------------

**Flexible Resolutions**  
- The job script is modified to support arbitrary combinations of horizontal and vertical resolutions. Changes to magnetic grids are also supported.

**Extended Upper Boundary**  
- Job script, defs.h, and initialization of some altitude-dependent variables (xfac, ar_glbm, aureff, bdriz) are rewritten to support the extension of the upper boundary.

**High Cadence Model Time**  
- Model time for input/output is set to 4 digits (day/hour/minute/second) instead of the old 3-digit format (day/hour/minute) to allow higher cadence.

**Unified N2 Calculations**  
- The calculation of N2 mixing ratio, mean molecular mass, and scale height is unified to avoid recalculations. Some artificial caps on N2 mixing ratio are removed.

**Rewritten Helium Module**  
- The Helium module is rewritten and now included with all resolutions (default on).

**Ring Filter**  
- The old Fourier filter is replaced with a new ring filter.

**O+ Sub-Cycling**  
- An additional input parameter NSTEP_SUB is introduced to control the number of O+ sub-cycling.

**NetCDF4 Parallel IO**  
- NetCDF4 parallel IO is enabled to reduce memory usage on the root task.

**Bit-for-Bit Reproducibility**  
- ESMF calls are modified to ensure bit-for-bit reproducibility.

**Updated IGRF**  
- The geomagnetic field is updated to the latest International Geomagnetic Reference Field version.

**Rewritten Magnetospheric Coupling Module**  
- The magnetospheric coupling module is rewritten to support in-memory MPI data transfer.

**Code Simplifications**  
- Unused parameters, arguments, and variables are removed from some functions to simplify the code.

**MPI Subroutine Optimizations**  
- Some MPI subroutines are rewritten for a speed boost.

**Consistent Dipmin Calculation**  
- Dipmin is set to sin(dlat*2*dtr) instead of being manually set for different resolutions.

**Miscellaneous Bug Fixes**  
- Various minor bug fixes.

Changes in Physics
------------------

**Solar Heating Coefficients**  
- Modified coefficients of solar heating (Astrid Maute).

**Height Variation of Equatorward Electric Field**  
- A scaling factor is added to account for the height variation of the equatorward electric field (elam) (Astrid Maute).

**Field-Aligned Ion Drag**  
- Field-aligned ion drag is included in the momentum equation (Jiuhou Lei).

**Electron Heat Flux Parameterization**  
- The parameterization scheme of electron heat flux (fed) near the equator is changed in settei (Tong Dang).

**Thermal Electron Heating Efficiency**  
- A sixth-order polynomial is used for thermal electron heating efficiency (Yihui Cai).

**Electrojet Turbulent Heating**  
- Electrojet turbulent heating is introduced, default off (Jing Liu).

**Empirical SAPS**  
- Empirical SAPS is introduced, default off (Cheng Sheng).

**Eclipse Solar EUV Masking**  
- Support for eclipse solar EUV masking is added (Tong Dang).

**Lower Boundary Forcing by External Data**  
- Support for lower boundary forcing by external data (SD nudging, Haonan Wu).

For any questions or further information, please contact the discussion group email list at tgcmgroup@ucar.edu.
