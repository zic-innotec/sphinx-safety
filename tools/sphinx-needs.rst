Sphinx-Needs
============

.. tool:: Sphinx-Needs
   :id: TOOL_SPHINX-NEEDS
   :version: 5.1.0, 4.2.0
   :status: in_progress

   Sphinx makes it easy to create intelligent and beautiful
   documentation.

   :Documentation: https://www.sphinx-needs.com
   :Code: https://github.com/useblocks/sphinx-needs

.. dropdown:: 📊 Object analysis

   .. needflow::
      :filter: "Sphinx-Needs" in sections

   .. needtable::
      :filter: "Sphinx-Needs" in sections
      :columns: id, title, type

   .. needpie:: Sphinx-Needs objects
      :legend: 
      :labels: Features, Errors, Restrictions, Checks, Steps
      :explode: 0,0,0,0.1,0.1

      type == "feature" and "Sphinx-Needs" in sections
      type == "error" and "Sphinx-Needs" in sections
      type == "restriction" and "Sphinx-Needs" in sections
      type == "check" and "Sphinx-Needs" in sections
      type == "step" and "Sphinx-Needs" in sections

.. dropdown:: ✅ Compliance statistics

   Features without errors:
   :need_count:`"Sphinx-Needs" in sections and type == "feature" and len(parent_needs_back) == 0` /
   :need_count:`"Sphinx-Needs" in sections and type == "feature"`

   Errors without a mitigation: 
   :need_count:`"Sphinx-Needs" in sections and type == "error" and (len(avoids_back) == 0 and len(checks_back) == 0)` /
   :need_count:`"Sphinx-Needs" in sections and type == "error"`

   Restrictions without error:
   :need_count:`"Sphinx-Needs" in sections and type == "restriction" and len(avoids) == 0` /
   :need_count:`"Sphinx-Needs" in sections and type == "restriction"`

   Checks without error:
   :need_count:`"Sphinx-Needs" in sections and type == "check" and len(checks) == 0` /
   :need_count:`"Sphinx-Needs" in sections and type == "check"`

Features
--------

.. feature:: Read Traceability objects in Sphinx-Needs
   :id: FE_SN_READ
   :tools: TOOL_SPHINX-NEEDS

   Read Traceability objects from rst/md files into the internal storage.

   .. error:: Syntax errors in rst/md files cause Traceability objects to be ignored
      :id: ER_SN_SYN_ER
      :td: 1

   .. error:: Missing external needs.json file
      :id: ER_SN_JSON_NOT_FOUND
      :td: 1

   .. error:: Corrupted external needs.json file
      :id: ER_SN_JSON_CORRUPTED
      :td: 1

   .. error:: Authentication issues with needsservice
      :id: ER_SN_SER_AUTH
      :td: 1

   .. error:: Invalid meta-data in rst/md files leads to ignored Traceability objects
      :id: ER_SN_DATA_INVALID
      :td: 1

   .. error:: Programmatic errors in rst/md files result in ignored Traceability objects
      :id: ER_SN_CODE_ERR
      :td: 1

   .. error:: Invalid or incorrect filters used for external needs.json
      :id: ER_SN_JSON_FILTER
      :td: 1

   .. error:: External service unreachable by needsservice
      :id: ER_SN_SER_DOWN
      :td: 1

   .. error:: needsservice unable to process data from external service
      :id: ER_SN_SER_INVALID
      :td: 1

.. feature:: Display Traceability objects content in Sphinx-Needs
   :id: FE_SN_CONTENT_RENDER
   :tools: TOOL_SPHINX-NEEDS

   .. error:: Content contains syntax errors
      :id: ER_SN_CONTENT_SYNTAX
      :td: 1

.. feature:: Assign meta-data to Traceability objects in Sphinx-Needs
   :id: FE_SN_SET_META
   :tools: TOOL_SPHINX-NEEDS

   .. error:: Dynamic functions return invalid meta-data
      :id: ER_SN_DYN_INVALID
      :td: 1

   .. error:: Dynamic functions return wrong meta-data
      :id: ER_SN_DYN_WRONG
      :td: 3

      Internal dynamic functions are checked by test-cases in Sphinx-Needs itself.

      But self-written dynamic functions can do whatever they want, as long as the returned data ist 
      still valid (but may be wrong).

      So self-written dynamic functions need test cases as well!

   .. error:: Sphinx-Needs data not valid
      :id: ER_SN_META_INVALID
      :td: 1

   .. error:: Sphinx-Needs data is not process-compliant
      :id: ER_SN_META_NOT_COMPLIANT
      :td: 1

.. feature:: Establish links between Traceability objects in Sphinx-Needs
   :id: FE_SN_LINK
   :tools: TOOL_SPHINX-NEEDS

   .. error:: Back-links are not set
      :id: ER_SN_LINKS_NO_BACK
      :td: 1

      Links are set only in one direction but not in the other.

      This may lead to missing information, e.g. a Traceability object is linked to a specification, but you 
      can't find the linked Traceability object during specification implementation.


   .. error:: Internal target link is not found
      :id: ER_SN_LINKS_NO_TARGET
      :td: 1

   .. error:: External needs not found
      :id: ER_SN_LINKS_NO_EXT
      :td: 1

   .. error:: External needs corrupted
      :id: ER_SN_LINKS_EXT_COR
      :td: 1

   .. error:: Links missing
      :id: ER_SN_LINKS_MISSING
      :td: 1

      Set links are not treated correctly and are not part of the final documentation.

      Sphinx-Needs shows a warning for all not found used need-IDs for links.

.. feature:: Generate object representation in Sphinx-Needs
   :id: FE_SN_DOCTREE
   :tools: TOOL_SPHINX-NEEDS

   .. error:: Meta-data missing
      :id: ER_SN_LAY_META_MIS
      :td: 1

      Needed meta-data is not part of the final representation in the doctree and so later HTML/PDF build

   .. error:: Wrong meta-data is used
      :id: ER_SN_LAY_META_WRONG
      :td: 1

      Sphinx-Needs is adding wrong Meta-Data to the final doctree-layout


.. feature:: Export needs.json file using Sphinx-Needs
   :id: FE_SN_JSON
   :tools: TOOL_SPHINX-NEEDS

   .. error:: Objects missing in needs.json
      :id: ER_SN_JSON_MIS
      :td: 1 

   .. error:: Traceability objects meta-data corrupted
      :id: ER_SN_JSON_COR
      :td: 1

Dynamic Content
~~~~~~~~~~~~~~~

.. feature:: Apply dynamic functions for meta-data computation
   :id: FE_SN_DYN_FUNC
   :tools: TOOL_SPHINX-NEEDS

   .. error:: Function gets not executed
      :id: ER_SN_DYN_NO_EXEC
      :td: 1

      The function gets not executed and in the generated documentation the dynamic-function string can be found.

   .. error:: Function returns invalid value
      :id: ER_SN_DYN_INVALID2
      :td: 1
      

      Function returns a technically not allowed value.

   .. error:: Function returns wrong calculated values
      :id: ER_SN_DYN_WRONG_CALC
      :td: 3

      The dynamic functions calculates wrong values

.. feature:: Extend page content with templates in Sphinx-Needs
   :id: FE_SN_TEMPLATE_PAGE
   :tools: TOOL_SPHINX-NEEDS

.. feature:: Enhance Need content using templates in Sphinx-Needs
   :id: FE_SN_TEMPLATE_NEED
   :tools: TOOL_SPHINX-NEEDS

Analysis
~~~~~~~~

.. feature:: Display filtered Need objects in a table format
   :id: FE_SN_TABLE
   :tools: TOOL_SPHINX-NEEDS

.. feature:: Visualize filter results with a pie chart
   :id: FE_SN_PIE
   :tools: TOOL_SPHINX-NEEDS

.. feature:: Output filter results as a numeric value in text
   :id: FE_SN_COUNT
   :tools: TOOL_SPHINX-NEEDS

Restrictions
------------

.. restriction:: Do not use dynamic functions
   :id: CHECK_SN_NO_DYN
   :avoids: ER_SN_DYN_INVALID, ER_SN_DYN_WRONG

   Dynamic functions can execute not qualified code, which has full access to all Sphinx-Needs data.
   So its execution can corrupt the data.

.. restriction:: Warning to Error
   :id: RE_SN_WARNINGS
   :avoids: ER_FILES_IGNORED, ER_SN_DATA_INVALID

   Always use the sphinx-build option ``-W`` to transform all warnings into errors,
   because only errors stop the build and set an exit code > 0.

.. restriction:: Clean full build 
   :id: RE_SN_CLEAN

   Always use a **clean** and **full** sphinx-build.
   An incremental build is not allowed, as not all files get updated by Sphinx.

   So before the ``sphinx-build`` command gets executed, the related ``build`` folder shall be deleted.
   Then ``sphinx-build`` shall be built with the options ``-a`` and ``-E`` to force Sphinx
   to read and write really all files. 

Artifacts
---------
