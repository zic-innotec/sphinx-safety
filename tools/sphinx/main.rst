Sphinx
======

.. tool:: Sphinx
   :id: TOOL_SPHINX
   :version: 7.4.7, 8.2.3
   :status: in_progress

   Sphinx makes it easy to create intelligent and beautiful
   documentation.

   :Documentation: https://www.sphinx-doc.org/en/master/
   :Code: https://github.com/sphinx-doc/sphinx

Analysis
--------

.. needflow::
   :filter: "tools/sphinx/" in docname

.. needtable::
   :filter: "tools/sphinx/" in docname
   :columns: id, title, type

.. needpie::
   :legend:
   :labels: Features, Errors, Restrictions, Checks, Steps
   :explode: 0,0,0,0.1,0.1

   type == "feature" and "tools/sphinx/" in docname
   type == "error" and "tools/sphinx/" in docname
   type == "restriction" and "tools/sphinx/" in docname
   type == "check" and "tools/sphinx/" in docname
   type == "step" and "tools/sphinx/" in docname

.. dropdown:: ✅ Compliance statistics

   Features without errors: :need_count:`"tools/sphinx/" in docname and type == "feature" and len(parent_needs_back) == 0`
   / :need_count:`"tools/sphinx/" in docname and type == "feature"`

   Errors without a mitigation: :need_count:`"tools/sphinx/" in docname and type == "error" and (len(avoids_back) == 0 and len(checks_back) == 0)`
   / :need_count:`"tools/sphinx/" in docname and type == "error"`

   Restrictions without error: :need_count:`"Sphinx" in sections and type == "restriction" and len(avoids) == 0`
   / :need_count:`"tools/sphinx/" in docname and type == "restriction"`

   Checks without error: :need_count:`"Sphinx" in sections and type == "check" and len(checks) == 0`
   / :need_count:`"tools/sphinx/" in docname and type == "check"`
