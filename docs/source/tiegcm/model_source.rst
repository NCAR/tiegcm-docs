Model Source Code
=================

Source Code Location
--------------------

The source code of the model is located in the ``src/`` subdirectory within the model root directory, commonly referred to as ``modeldir``, which is included in the model download package.

Academic License Agreement
--------------------------

The TIEGCM is governed by an Open Source Academic Research License Agreement provided by NCAR/UCAR, which stipulates the conditions under which the model, including its source code, may be used for research, academic, and non-profit purposes.

Source Code Documentation
-------------------------

* **Warning**: Diagrams provided may be outdated as of TIEGCM version 2.0.
* Detailed flow diagrams of the source code structure are available:
  - `TIEGCM Code Structure (multi-page pdf) <http://www.hao.ucar.edu/modeling/tgcm/download/files/tiegcm_codestruct.pdf>`
  - `TIEGCM Code Structure (single-page pdf) <http://www.hao.ucar.edu/modeling/tgcm/download/files/tiegcm_code_poster.pdf>`

Modifying the Source Code
-------------------------

Users such as community members, students, researchers, or developers are encouraged to modify the source code to suit their specific needs. After initial setup and a default model run as outlined in the QuickStart Section:

1. Navigate to the ``src/`` subdirectory within ``modeldir``.
2. Modify the source files as required.
3. Rebuild the model by executing the job script in ``workdir`` or by running ``gmake`` in ``execdir`` to recompile and execute the model.
