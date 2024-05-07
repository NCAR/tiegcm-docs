Thermosphere Ionosphere Electrodynamics General Circulation Model
=================================================================

Functional Description - TIE-GCM
--------------------------------

The NCAR Thermosphere-Ionosphere-Electrodynamics General Circulation Model (TIE-GCM) is a comprehensive, first-principles, three-dimensional, non-linear representation of the coupled thermosphere and ionosphere system that includes a self-consistent solution of the middle and low-latitude dynamo field.

The model solves the three-dimensional momentum, energy and continuity equations for neutral and ion species at each time step, using a semi-implicit, fourth-order, centered finite difference scheme on each pressure surface in a staggered vertical grid. It can be run in either serial or parallel mode on a variety of platforms, including Linux workstations and supercomputers. The time step is typically 120 s.

Grid Parameters
---------------

The standard low-resolution grid parameters are:

- Spherical geographic coordinates
- Latitude: -87.5° to 87.5° in 5° increments
- Longitude: -180° to 180° in 5° increments
- Altitude: Pressure levels from -7 to +7 in increments of H/2.
- Lower boundary: ~97 km
- Upper boundary: ~500 to ~700 km depending on solar activity

Strengths
---------

- Accurate, self-consistent calculation of coupled thermosphere and ionosphere system
- Calculates all important aeronomic parameters and minor species
- Solar forcing can be specified by proxy models or measurements
- Auroral forcing can be specified by empirical relationships, by output from the AMIE procedure, or by a magnetosphere model such as the LFM.

Assumptions
-----------

- Hydrostatic assumption, constant gravity, steady-state ion and electron energy equations. Ion momentum equations are not solved explicitly; ion velocities are obtained from ExB drifts. Hydrogen and helium and their ions are not presently included in the model. A simplified relationship is used for photoelectron heating. The upper boundary conditions for electron heat and flux transfer are simple empirical specifications. CO2 is not solved explicitly but is specified assuming diffusive equilibrium. Eddy diffusion uses a simplified formulation.

Inputs
------

- F10.7 daily index and its 81-day centered mean.
- Kp index; or IMF and Solar Wind; or specified cross-cap potential and hemispheric power.

Outputs
-------

Output fields specified in 3 spatial dimensions plus time:

- GEOPOTENTIAL: Height of pressure surfaces (cm)
- TEMPERATURE: Neutral, ion, electron (K)
- NEUTRAL WINDS: zonal, meridional, vertical (m/s)
- COMPOSITION: O, O2, NO, N(4S), N(2D), O+, O2+, N2+, NO+, N+, Ne
- POTENTIAL: In geomagnetic and geographic coordinates

Hardware and Software Requirements
----------------------------------

The TIEGCM can be run in either parallel or serial mode on a variety of platforms, including IBM systems running AIX, Linux cluster systems, and Linux workstations. The code is written in standard FORTRAN-90 and requires MPI and netCDF libraries. Input and output files are in netCDF format.