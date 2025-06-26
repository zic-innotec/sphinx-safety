Restrictions
============

.. restriction:: Do not use dynamic functions
   :id: CHECK_SN_NO_DYN
   :avoids: ER_SN_DYN_INVALID, ER_SN_DYN_WRONG

   Dynamic functions can execute not qualified code, which has full
   access to all Sphinx-Needs data. So its execution can corrupt the
   data.

.. restriction:: Warning to Error
   :id: RE_SN_WARNINGS
   :avoids: ER_FILES_IGNORED, ER_SN_DATA_INVALID

   Always use the sphinx-build option ``-W`` to transform all warnings
   into errors, because only errors stop the build and set an exit code >
   0.

.. restriction:: Clean full build
   :id: RE_SN_CLEAN

   Always use a **clean** and **full** sphinx-build. An incremental build
   is not allowed, as not all files get updated by Sphinx.

   So before the ``sphinx-build`` command gets executed, the related ``build``
   folder shall be deleted. Then ``sphinx-build`` shall be built with the
   options ``-a`` and ``-E`` to force Sphinx to read and write really all
   files.
