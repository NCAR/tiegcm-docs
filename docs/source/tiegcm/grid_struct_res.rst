Grid Structure and Resolution
=============================

The TIEGCM can be configured for various combinations of spatial/temporal resolutions (use the horires/vertres shell variable in the job script to set the model resolution):

- Horizontal resolutions: 5/2.5/1.25/0.625 degrees lat x lon, default time step = 60/30/10/5 secs
- Vertical resolutions: 2/4/8/16 grid points per scale height

The vertical coordinate lev, or Zp, is a log-pressure scale ln(p0/p), where p is pressure and p0 is a reference pressure. Fields are calculated at either "interface" levels (ilev), or at "midpoint" levels (lev) (see lev and ilev coordinate definitions below).

- At 1/2 scale height, Zp at interfaces = -7 to +7 by 0.5
- At 1/4 scale height, Zp at interfaces = -7 to +7 by 0.25
- At 1/8 scale height, Zp at interfaces = -7 to +7 by 0.125
- At 1/16 scale height, Zp at interfaces = -7 to +7 by 0.0625

Note: To interpolate model fields to constant height surfaces, you should use geometric height, which is available on the 3d model grid as "ZG" on secondary histories. See the section below on Altitude Coordinates the NCAR TIEGCM for a detailed explanation of the relationship between Zp and Altitude.

Geographic 3d spatial coordinates at 5-degree resolution
--------------------------------------------------------

Following are spatial coordinates for the 5x5-degree latxlon horizontal grid:

Dimensions:

- lon = 72
- lat = 36

Coordinates:

- lon = 180W (-180) to 175E (175) by 5 degrees
- lat = 87.5S (-87.5) to 87.5N (87.5) by 5 degrees

Geographic 3d spatial coordinates at 2.5-degree resolution
----------------------------------------------------------

Following are spatial coordinates for the 2.5x2.5-degree latxlon horizontal grid:

Dimensions:

- lon = 144
- lat = 72

Coordinates:

- lon = 180W (-180) to 177.5E (177.5) by 2.5 degrees
- lat = 88.75S (-88.75) to 88.75N (88.75) by 2.5 degrees

Geographic 3d spatial coordinates at 1.25-degree resolution
----------------------------------------------------------

Following are spatial coordinates for the 1.25x1.25-degree latxlon horizontal grid:

Dimensions:

- lon = 288
- lat = 144

Coordinates:

- lon = 180W (-180) to 178.75E (178.75) by 1.25 degrees
- lat = 88.75S (-89.375) to 88.75N (89.375) by 1.25 degrees

Geographic 3d spatial coordinates at 0.625-degree resolution
----------------------------------------------------------

Following are spatial coordinates for the 0.625x0.625-degree latxlon horizontal grid:

Dimensions:

- lon = 576
- lat = 288

Coordinates:

- lon = 180W (-180) to 178.75E (179.375) by 0.625 degrees
- lat = 88.75S (-89.6875) to 88.75N (89.6875) by 0.625 degrees

Geographic 3d spatial coordinates at 1/2-scale height resolution
----------------------------------------------------------

Following are spatial coordinates for the 1/2-scale height vertical grid:

Dimensions:

- lev = 29
- ilev = 29

Coordinates:

- lev = -6.75 to 7.25 by 1/2 scale height
- ilev = -7 to 7 by 1/2 scale height

Geographic 3d spatial coordinates at 1/4-scale height resolution
----------------------------------------------------------

Following are spatial coordinates for the 1/4-scale height vertical grid:

Dimensions:

- lev = 57
- ilev = 57

Coordinates:

- lev = -6.875 to 7.125 by 1/4 scale height
- ilev = -7 to 7 by 1/4 scale height

Geographic 3d spatial coordinates at 1/8-scale height resolution
----------------------------------------------------------

Following are spatial coordinates for the 1/8-scale height vertical grid:

Dimensions:

- lev = 113
- ilev = 113

Coordinates:

- lev = -6.9375 to 7.0625 by 1/8 scale height
- ilev = -7 to 7 by 1/8 scale height

Geographic 3d spatial coordinates at 1/8-scale height resolution
----------------------------------------------------------

Following are spatial coordinates for the 1/16-scale height vertical grid:

Dimensions:

- lev = 225
- ilev = 225

Coordinates:

- lev = -6.96875 to 7.03125 by 1/16 scale height
- ilev = -7 to 7 by 1/16 scale height

Geomagnetic 3d spatial coordinates
----------------------------------

The longitude geomagnetic coordinate is from -180 to +180 by 4.5/2.25/1.125 degrees. The latitude coordinate is non-regular, with resolution increasing toward the magnetic equator. The vertical Zp (ln(p0/p)) interface coordinate is from -8.5 to 7 by 0.5/0.25/0.125/0.0625:

Dimensions:

- mlon = 81/161/321
- mlat = 97/193/385
- mlev = 32/63/125/249
- imlev = 32/63/125/249

Coordinates:

- mlon = 180W (-180) to 180E (180) by 4.5/2.25/1.125 degrees
- mlat = 90S (-90) to 90N (90): irregular, increasing resolution equatorward
- mlev = -8.25 to 7.25 by 0.5/0.25/0.125/0.0625
- imlev = -8.5 to 7.0 by 0.5/0.25/0.125/0.0625


Altitude Coordinates in the NCAR TIE-GCM and TIME-GCM
----------------------------------
The purpose of this document is to define the altitude coordinate systems used in the NCAR Thermosphere-Ionosphere-Electrodynamics General Circulation Model (TIE-GCM) and Thermosphere-Ionosphere-Mesosphere-Electrodynamics General Circulation Model (TIME-GCM), especially to inform model users as to how to register model output in the vertical dimension.

The TIE-GCM and TIME-GCM use a log-pressure coordinate system, with each pressure level defined as ln(P0/P), where P0 = 5x10-4 dynes/cm2 = 5x10-5 Pascal = 5x10-7 hPa = 5x10-7 mb. (Native units in these models are cgs, i.e., dynes/cm2.) This pressure occurs at ~200 km altitude, depending on conditions.

The TIE-GCM vertical coordinate extends from -7 to +7 (~97 km to ~600 km) and the TIME-GCM vertical coordinate extends from -17 to +7 (~30 km to ~600 km):

.. list-table::
   :widths: 40 15 15 15 15 15 15
   :header-rows: 1

   * - Model/Resolution
     - Num Levels
     - Level Spacing
     - Bottom Level
     - Top Level
     - Min Alt
     - Max Alt
   * - 1/2 scale hiehgt-Res TIE-GCM
     - 29
     - 0.5
     - -7
     - +7
     - 97 km
     - 600 km
   * - 1/4 scale height-Res TIE-GCM
     - 57
     - 0.25
     - -7
     - +7
     - 97 km
     - 600 km
   * - 1/8 scale height-Res TIE-GCM
     - 113
     - 0.125
     - -7
     - +7
     - 97 km
     - 600 km
   * - 1/16 scale height-Res TIE-GCM
     - 225
     - 0.0625
     - -7
     - +7
     - 97 km
     - 600 km
   * - 1/2 scale height-Res TIME-GCM
     - 49
     - 0.5
     - -17
     - +7
     - 30 km
     - 600 km
   * - 1/4 scale height-Res TIME-GCM
     - 97
     - 0.25
     - -17
     - +7
     - 30 km
     - 600 km
   * - 1/8 scale height-Res TIME-GCM
     - 193
     - 0.125
     - -17
     - +7
     - 30 km
     - 600 km
   * - 1/16 scale height-Res TIME-GCM
     - 385
     - 0.0625
     - -17
     - +7
     - 30 km
     - 600 km

The height of the pressure surface is defined at each grid point in arrays provided in output history files (in cm). Unfortunately, there are four different possibilities for altitude definition, all slightly different.

First, we define the geopotential height z. Geopotential height is the height that the pressure surface would be, assuming that the acceleration due to gravity g is constant at the value used in the model calculations (870 cm/s2 for the TIE-GCM and 950 cm/s2 for the TIME-GCM). It is registered to the altitude of the model lower boundary, which can vary horizontally due to the tidal and climatological lower boundary specification. This is the native coordinate system for the models, and so z is included in all history files. However, it is not the appropriate altitude coordinate for comparison with real-world data. Also note that this definition of geopotential height is not the same as what is used in, e.g., tropospheric meteorology, because it is referenced to value of g that is different from the value of g at the surface (~980 cm/s2).

We can correct the geopotential height z to obtain geometric height zg. This is performed inside the models by subroutine calczg (addiag.F), using an empirical formulation of the variation of g over the globe (including centripetal force), and vertical integration, to account for the variation with altitude. It can also be done, using the same subroutine, in the Fortran model processers, and is also available in various IDL processing routines. Geometric height ZG is now forced onto secondary histories (i.e., it is output whether you request it or not) but not on primary histories (because primary histories contain only what is necessary to re-start the model). However, some older secondary history files may not include ZG which necessitates that it be calculated in the post-processing if needed for data comparison.

Now we come to the final complication, which is the distinction between model interfaces and model mid-points. The interfaces are the native coordinate system of the model grid, as defined in the table above, i.e., at -7.0, -6.5, -6.0, etc.; z and zg are defined on these interfaces. However, most model output quantities are actually reported at the midpoints, half-way between interfaces in pressure, i.e., at -6.75, -6.25, -5.75, etc. Each midpoint is a half-interval above the corresponding interface. All temperatures, winds, neutral compositions, etc., are defined at these midpoints. However, electron density and electric potential are defined at the interfaces:

.. list-table:: Field Specifications
   :widths: 10 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
   :header-rows: 1

   * - Field
     - Tn
     - Un
     - Vn
     - O2
     - O1
     - He
     - O+
     - N(2D)
     - N(4S)
     - NO
     - Ar
     - Ti
     - Te
     - Ne
     - Omega
     - O2+
     - Z
     - Poten
     - Zg
     - Zm
   * - Specified at
     - M
     - M
     - M
     - M
     - M
     - M
     - M
     - M
     - M
     - M
     - M
     - M
     - M
     - I
     - M
     - M
     - I
     - I
     - I
     - M

In order to register midpoint quantities in altitude, it is therefore necessary to interpolate from the midpoints to the interfaces. Alternatively, it may be simpler to interpolate zg from the interfaces to the midpoints. For TIE-GCM 2.0, a new output variable has been added, ZGMID, which is geometric height that has been interpolated to the mid points. However, older history files do not include ZGMID. As with ZG, it is available on secondary histories but not on primary histories.

In output histories, quantities specified at interfaces are defined by the ilev coordinate variable and quantities specified at midpoints are defined by the lev coordinate variable. These quantities are generally numerically identical, but their definitions in the files can serve as a reminder of what is defined where.

Height-related Variables on TIEGCM Secondary Histories:

.. note:: Variables Z, ZG, and ZMAG are forced onto secondary histories. To save ZGMID to secondary histories, add ZGMID to the fields list in the namelist input file: SECFLDS='ZGMID'

.. list-table:: Variable Descriptions
   :widths: 10 30
   :header-rows: 1

   * - Variable Name
     - Description
   * - Z
     - Geopotential Height (cm)
   * - ZG
     - Geometric Height (cm)
   * - ZGMID
     - Geometric Height at Midpoints (cm)
   * - ZMAG
     - Geopotential Height on Geomagnetic Grid (km)


