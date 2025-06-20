Sphinx
======

.. tool:: Sphinx 
   :id: TOOL_SPHINX 
   :version: 7.4.7, 8.2.3
   :status: in_progress

   Sphinx makes it easy to create intelligent and beautiful documentation.

   :Documentation: https://www.sphinx-doc.org/en/master/
   :Code: https://github.com/sphinx-doc/sphinx

.. dropdown:: 📊 Object analysis

   .. needflow::
      :filter: "Sphinx" in sections

   .. needtable::
      :filter: "Sphinx" in sections
      :columns: id, title, type

   .. needpie::
      :legend: 
      :labels: Features, Errors, Restrictions, Checks, Steps
      :explode: 0,0,0,0.1,0.1

      type == "feature" and "Sphinx" in sections
      type == "error" and "Sphinx" in sections
      type == "restriction" and "Sphinx" in sections
      type == "check" and "Sphinx" in sections
      type == "step" and "Sphinx" in sections

.. dropdown:: ✅ Compliance statistics

   Features without errors:
   :need_count:`"Sphinx" in sections and type == "feature" and len(parent_needs_back) == 0` /
   :need_count:`"Sphinx" in sections and type == "feature"`
   
   Errors without a mitigation: 
   :need_count:`"Sphinx" in sections and type == "error" and (len(avoids_back) == 0 and len(checks_back) == 0)` /
   :need_count:`"Sphinx" in sections and type == "error"`

   Restrictions without error:
   :need_count:`"Sphinx" in sections and type == "restriction" and len(avoids) == 0` /
   :need_count:`"Sphinx" in sections and type == "restriction"`

   Checks without error:
   :need_count:`"Sphinx" in sections and type == "check" and len(checks) == 0` /
   :need_count:`"Sphinx" in sections and type == "check"`

Features
--------


.. feature:: Read-in documents with Sphinx
   :id: FE_SPHINX_READ
   :tools: TOOL_SPHINX

   Readin all needed rst/md files for the Sphinx project.

   .. error:: Needed folders/files are ignored
      :id: ER_FILES_IGNORED
      :td: 1 

      Error is logged by Sphinx and with build-option ``-W``
      this warning gets thrown as error and stops the build.

   .. error:: Needed files/folders have not supported encoding
      :id: ER_SPH_WRONG_ENCODING
      :td: 1
   
   .. error:: Access to files/folders not given
      :id: ER_SPH_WRONG_ACCESS
      :td: 1



Restrictions
------------

.. restriction:: Warning to Error
   :id: RE_SPHINX_WARNINGS
   :avoids: ER_FILES_IGNORED, ER_SPH_WRONG_ENCODING, ER_SPH_WRONG_ACCESS

   Always use the sphinx-build option ``-W`` to transform all warnings into errors,
   because only errors stop the build and set an exit code > 0.

.. restriction:: Clean full build 
   :id: RE_SPHINX_CLEAN
   
   Always use a **clean** and **full** sphinx-build.
   An incremental build is not allowed, as not all files get updated by Sphinx.

   So before the ``sphinx-build`` command gets executed, the related ``build`` folder shall be deleted.
   Then ``sphinx-build`` shall be built with the options ``-a`` and ``-E`` to force Sphinx
   to read and write really all files. 

Artifacts
---------
