
Codelinks
============

.. tool:: Codelinks
   :id: TOOL_SCL
   :version: 1.0.0.
   :status: in_progress

   Sphinx-CodeLinks is a lightweight solution for enabling 
   traceability between source code and documentation.

   :Documentation: https://codelinks.useblocks.com/
   :Code: https://github.com/useblocks/sphinx-codelinks

Analysis
--------


.. needflow::
   :filter: "tools/sphinx-codelinks/" in docname

.. needtable::
   :filter: "tools/sphinx-codelinks/" in docname
   :columns: id, title, type

.. needpie:: Sphinx-CodeLinks objects
   :legend:
   :labels: Features, Errors, Restrictions, Checks, Steps
   :explode: 0,0,0,0.1,0.1

   type == "feature" and "tools/sphinx-codelinks/" in docname
   type == "error" and "tools/sphinx-codelinks/" in docname
   type == "restriction" and "tools/sphinx-codelinks/" in docname
   type == "check" and "tools/sphinx-codelinks/" in docname
   type == "step" and "tools/sphinx-codelinks/" in docname

.. dropdown:: ✅ Compliance statistics

   Features without errors: :need_count:`"tools/sphinx-codelinks/" in docname and type == "feature" and len(parent_needs_back) == 0`
   / :need_count:`"tools/sphinx-codelinks/" in docname and type == "feature"`

   Errors without a mitigation: :need_count:`"tools/sphinx-codelinks/" in docname and type == "error" and (len(avoids_back) == 0 and len(checks_back) == 0)`
   / :need_count:`"tools/sphinx-codelinks/" in docname and type == "error"`

   Restrictions without error: :need_count:`"tools/sphinx-codelinks/" in docname and type == "restriction" and len(avoids) == 0`
   / :need_count:`"tools/sphinx-codelinks/" in docname and type == "restriction"`

   Checks without error: :need_count:`"tools/sphinx-codelinks/" in docname and type == "check" and len(checks) == 0`
   / :need_count:`"tools/sphinx-codelinks/" in docname and type == "check"`
