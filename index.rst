:sd_hide_title:
:hide-toc:

Introduction
============

.. grid::
   :class-row: sd-w-100

   .. grid-item::
      :columns: 12 8 8 8
      :child-align: justify
      :class: sd-fs-3

      .. div:: sd-font-weight-bold

         Classification for  Sphinx + X

      .. div:: sd-fs-5 sd-font-italic

         Qualify your Sphinx-based documentation toolchain for safety audits
         requested by ISO 26262, IEC 61508, EN 50716, and more.

      .. grid:: 1 1 2 2
         :gutter: 2 2 3 3
         :margin: 2
         :padding: 0

         .. grid-item::
            :columns: auto

            .. button-ref:: usage/quickstart
               :ref-type: doc
               :outline:
               :color: primary
               :class: sd-rounded-pill sd-px-4 sd-fs-5

               Get Started

         .. grid-item::
            :columns: auto

            .. button-link:: https://useblocks.com/
               :outline:
               :color: primary
               :class: sd-rounded-pill sd-px-4 sd-fs-5

               Qualification Support

This documentation provides the needed information to get a
"qualification readiness" in any Sphinx-based project. It provides ``use cases``,
``features``, ``errors`` and ``restrictions`` as `Sphinx-Needs <https://sphinx-needs.com>`__
objects.

The classification is the basement for any qualification, which is
also covered by a commercial package provided by `useblocks <https://useblocks.com>`__
and `Innotec <https://innotecsafety.com/>`__.

Supported standards
-------------------

This documentation provides needed information for the Classifications
of Sphinx + Sphinx-Needs for the following standards:

* **Automotive**: `ISO 26262 <https://en.wikipedia.org/wiki/ISO_26262>`__
* **Automation, Industrial**: `IEC 61508 <https://en.wikipedia.org/wiki/IEC_61508>`__
* **Railway**: `EN 50716 <https://www.dinmedia.de/de/norm/din-en-50716/378381071>`__
* **Medical**: `IEC 62304 <https://en.wikipedia.org/wiki/IEC_62304>`__
* **Agriculture**: `ISO 25119 <https://en.wikipedia.org/wiki/ISO_25119>`__
* Others can be added on request or by a Pull request.

.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: Basics

   usage/quickstart
   usage/index
   usage/contribute
   usage/qualification
   usage/license

.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: Classification Data
   
   use_cases/index
   tools/index
   analysis/index
