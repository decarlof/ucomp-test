==============
Repo structure
==============

- The ``analysis`` directory contains scripts that perform various analysis of pipeline output.

- The ``bin`` directory contains executable scripts that run the pipeline and   perform other maintenance tasks.

- The ``cmake`` directory contains some CMake modules for the build process. 
- The ``config`` directory contains the specification for the config file that controls the options for running the pipeline.
- The ``docs`` directory contains some documentation.
- The ``gen`` directory contains routines that are generally useful for MLSO instrument pipelines.
- The ``lib`` directory contains more general library routines not written by MLSO.
- The ``regression`` directory contains code specifically for the regression tests.
- The ``resource`` directory contains non-source code files used by the pipeline: distortion correction coefficients, demodulation coefficients, the epochs file, information about the wave regions, database table specifications, color tables, hot pixel locations, file validation specifications, and logo images.
- The ``scripts`` directory contains scripts that are run to maintain the repo: create the documentation, run the unit tests, find SSW dependencies, etc.
- The ``src`` directory contains all the UCoMP-specific pipeline code.
- The ``ssw`` directory contains SolarSoft routines needed for the pipeline. Only the routines necessary for the pipeline are included and are not automatically updated so that the pipeline does not break if SolarSoft is updated.
- The ``unit`` directory contains the unit tests.
