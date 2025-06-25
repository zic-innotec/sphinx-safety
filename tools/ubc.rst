ubc
===

.. tool:: ubc
   :id: TOOL_UBC
   :status: in_progress

   Command-line tool for checking and formating certain rules in sphinx
   and rst-based files.

   Little brother of :need:`TOOL_UBCODE`.

   **Commercial tool**

   :Documentation: https://ubcode.useblocks.com/ubc/introduction.html

.. dropdown:: 📊 Object analysis

   .. needflow::
      :filter: "ubc" in sections

   .. needtable::
      :filter: "ubc" in sections
      :columns: id, title, type

   .. needpie:: Sphinx-Needs objects
      :legend: 
      :labels: Features, Errors, Restrictions, Checks, Steps
      :explode: 0,0,0,0.1,0.1

      type == "feature" and "ubc" in sections
      type == "error" and "ubc" in sections
      type == "restriction" and "ubc" in sections
      type == "check" and "ubc" in sections
      type == "step" and "ubc" in sections

.. dropdown:: ✅ Compliance statistics

   Features without errors:
   :need_count:`"ubc" in sections and type == "feature" and len(parent_needs_back) == 0` /
   :need_count:`"ubc" in sections and type == "feature"`

   Errors without a mitigation: 
   :need_count:`"ubc" in sections and type == "error" and (len(avoids_back) == 0 and len(checks_back) == 0)` /
   :need_count:`"ubc" in sections and type == "error"`

   Restrictions without error:
   :need_count:`"ubc" in sections and type == "restriction" and len(avoids) == 0` /
   :need_count:`"ubc" in sections and type == "restriction"`

   Checks without error:
   :need_count:`"ubc" in sections and type == "check" and len(checks) == 0` /
   :need_count:`"ubc" in sections and type == "check"`

Features
--------

.. feature:: Check rst files for linting problems
   :id: FE_UBC_LINTING
   :tools: TOOL_UBC
   :inputs: ART_SPHINX_RST
   :td: 1

   .. error:: Not covered format
      :id: ER_UBC_LINTING_NOT_COVERED
      :td: 1

.. feature:: Format rst files
   :id: FE_UBC_FORMAT
   :tools: TOOL_UBC
   :td: 1

   .. error:: Format introduces errors
      :id: ER_UBC_FORMAT_ERRORS
      :td: 1

.. feature:: Clean internal caches
   :id: FE_UBC_CACHE
   :tools: TOOL_UBC
   :td: 1

.. feature:: Build needs.json
   :id: FE_UBC_BUILD_JSON
   :tools: TOOL_UBC
   :inputs: ART_SPHINX_RST
   :outputs: ART_UBC_NEEDS_JSON
   :td: 3

   .. error:: Incomplete data
      :id: ER_UBC_JSON_INCOMPLETE
      :td: 3

      This can have several reasons:

      * Not supported or unknown Sphinx-Needs directives. Like

        * list2needs

      * Not supported features of Sphinx-Needs. Like

        * dynamic functions

      * Unknown script executions
      * Unknown/not accessible sources, like

        * external services
        * import of needs.json files
        * unknown rst files

.. feature:: Validate needs.json
   :id: FE_UBC_VALIDATE_JSON
   :tools: TOOL_UBC
   :inputs: ART_UBC_NEEDS_JSON
   :td: 1

   .. error:: Unknown file format
      :id: ER_UBC_VAL_FORMAT
      :td: 1

   .. error:: Incomplete Validation
      :id: ER_UBC_VAL_INCOMPLETE
      :td: 1

      Not all types and options, which are represetned in a given needs.json
      file, are known/defined by the ``ubproject.toml`` configuration.

Restrictions
------------

.. restriction:: Do not use dynamic functions
   :id: CHECK_UBC_NO_DYN
   :avoids: ER_UBC_JSON_INCOMPLETE

.. restriction:: Do not use list2needs
   :id: CHECK_UBC_NO_LIST2NEEDS
   :avoids: ER_UBC_JSON_INCOMPLETE

.. restriction:: Do not use/reference rst files outside the ubproject workspace/scope
   :id: CHECK_UBC_RST_WORKSPACE
   :avoids: ER_UBC_JSON_INCOMPLETE

Artifacts
---------

.. artifact:: ubc needs.json file
   :id: ART_UBC_NEEDS_JSON

   A json file containing Sphinx-Needs objects.

   Often used to share requirements and co. in a technical way without
   the whole documentation project.

   Created by :need:`TOOL_UBC`, 
   which result is totally independant from :need:`TOOL_SN`.