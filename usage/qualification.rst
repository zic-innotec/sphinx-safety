.. _qualification:

:octicon:`shield-check` Qualification Kit
=========================================

To achieve a successful audit and final toolchain qualification,
additional information and tools are required. These are not part of
this classification document.

The required information is provided through a Qualification Kit,
which includes:

* Additional test cases for Sphinx and Sphinx-Needs.
* Documentation of ``checks`` and ``process steps``, including links to
  the ``errors`` described in this document.
* A license for ``ubCode`` and its command-line tool ``ubc``, enabling
  specific checks in VS Code and CI environments.
* A Qualification Report generator to document the final qualification
  results (part of ``ubc``).
* Templates for setting up consistent Qualification documentation for
  other tools, both external and internal.

The Qualification documentation uses the same technical foundation as
this documentation, primarily Sphinx and Sphinx-Needs. Therefore, this
classification section can be seamlessly integrated into the
Qualification documentation to create a comprehensive report.

To obtain a Sphinx Qualification Kit, please contact `Innotec GmbH <https://innotecsafety.com/>`__
or `useblocks GmbH <https://useblocks.com>`__.

Showcase
--------

.. grid:: 2

  .. grid-item::

     .. figure:: /_static/qualification_kit_website_1.png
        :width: 99%
        :align: center

        Imported test cases of Sphinx 
  
  .. grid-item::

     .. figure:: /_static/qualification_kit_website_2.png
        :width: 99%
        :align: center

        Defined checks for Sphinx
      


Qualification Method
--------------------

Our qualification process primarily relies on the tools ``ubCode`` and
its command-line version ``ubc`` to recreate specific Sphinx artifacts
and verify them for discrepancies.

These tools are developed by separate teams using entirely different
technical foundations. If both tools produce identical outputs, the
results can be considered **safe**.

Additionally, the Qualification Kit verifies tool-specific test cases
for safety-critical features. If these test cases exist—either as part
of the Open-Source project or the Qualification Kit—and their
execution is successful (*green*), the feature can also be deemed **safe**.

For features that are deemed unsafe, the tool's execution must be
reviewed during or after its run. Special scripts are available for
this purpose, which can be integrated into CI pipelines, pre-commit
hooks, or used with ``ubCode`` to ensure the avoidance of unsafe
features.
