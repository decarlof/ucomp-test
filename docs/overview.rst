========
Overview
========

This is the API documentation for the UCoMP pipeline, the code responsible for
ingesting level 0 UCoMP files and producing higher level products, including the
the level 1 and level 2 products, as well as engineering products to monitor the
instrument.

Besides the IDL code found in subdirectories of the ``src`` directory enumerated
below, there are several other directories used heavily by the pipeline.

The ``bin`` directory contains executable scripts that run the pipeline and
perform other maintenance tasks. The ``ucomp`` script, created from ``ucomp.in``,
is the primary way of running the pipeline, filtering the log, displaying
information from a FITS file, and many other tasks. The entry points in the
IDL source code that are called directly from the ``ucomp`` scripts end in
``_wrapper.pro`` and take ``date`` and ``config_filename`` as arguments::

  src/calibrate/ucomp_calibration_wrapper.pro
  src/distribute/ucomp_l0_archive_wrapper.pro
  src/distribute/ucomp_l1_archive_wrapper.pro
  src/distribute/ucomp_l2_archive_wrapper.pro
  src/distribute/ucomp_archive_wrapper.pro
  src/eod/ucomp_eod_check_wrapper.pro
  src/eod/ucomp_eod_wrapper.pro
  src/realtime/ucomp_realtime_wrapper.pro
  src/reprocess/ucomp_clearday_wrapper.pro
  src/reprocess/ucomp_reprocess_wrapper.pro
  src/validate/ucomp_validate_file_wrapper.pro

The ``config`` directory contains the specification for the config file that
controls the options for running the pipeline. Config files that follow this
spec are also placed in the installation from this directory. These config
files provide necessary information such as where to find the raw files and
options such as how to combine cameras or whether to update the database.

The ``gen`` directory contains routines that are generally useful for MLSO
instrument pipelines.

The ``lib`` directory contains more general library routines not written by MLSO.

The ``resource`` directory contains non-source code files used by the pipeline:
distortion correction coefficients, demodulation coefficients, the epochs file,
information about the wave regions, database table specifications, color
tables, hot pixel locations, file validation specifications, and logo images.

The ``ssw`` directory contains SolarSoft routines needed for the pipeline. Only
the routines necessary for the pipeline are included and are not automatically
updated so that the pipeline does not break if SolarSoft is updated.


:Author:
  MLSO team

:Dirs:
  ./
    top level class representing any UCoM pipeline run and the UCoMP version
  calendar/
    date/time handling
  calibrate/
    photometric calibration routines, a method for caching flats/darks and
    requesting a flat or dark for application to a science image
  database/
    routines to add to the database
  display/
    routines to write image files as well as graphics routines
  distribute/
    routines to create tarballs, send files to the archive, send files to the
    web archive
  eod/
    top level routines for the end-of-day process
  fileio/
    routines to handle file input/output, including caching data read from
    files
  gbu/
    routines for finding the GBU (good-bad-ugly) of processed files
  geometry/
    routines for finding, storing, and using the geometry properties of an image
  level1/
    top level 1 processing routines
  level2/
    top level 2 processing routines
  quality/
    routines for finding the quality of raw files; quality determines if a file
    should be processed
  realtime/
    top level routines for the realtime process
  report/
    routines for producing engineering plots and reports
  reprocess/
    top level routines for a reprocess
  utils/
    miscellaneous routines that don't fit other categories
  validate/
    routines for validation: determining if a file is valid, i.e., it has
    the correct format, metadata, etc.
  verify/
    routines for verification: determining if the processing has been
    completed correctly for a day
