.. _contribute:

:octicon:`people` Contribute
============================

Basic principals
----------------

1. Only validate relevant use cases.
#. If tool error negligible compared to human error, no need for
   validation.​
#. Use comparison of diverse tools as argumentation.​
#. Re-use community tests as far as reasonable.​
#. There is no such thing like “proven in use” for newer versions.​

Classi & Qualification Model
----------------------------

This flow chart gives an overview about all available Sphinx-Needs
types and their linking.

.. image:: /_static/contribute_model_example.png
   :align: center

Reusing docs
------------

.. uml::
   :align: center

   node "Safety classification docs" as safety #0fbcf9
   card "needs.json" as json
   card "HTML-Page" as page
   node "Project X docs" as x #FF6666
   node "Project Y docs" as y #6666FF

   safety --> page
   safety --> json

   json --> x : needimport
   json --> y : needimport

TI, TD and TCL values
---------------------

The **Tool Impact (TI)** value is assigned at the ``use case`` level
and indicates whether the ``use case`` has a safety-relevant impact. A
value of **2** signifies a safety-relevant impact, while **1**
indicates no safety relevance.

The **Tool Error Detection (TD)** value must be defined for each ``error``
and represents the ability to detect the error. Detection can be
performed either technically or manually through reviews. A value of **1**
means the error is detected, while **3** indicates the error is not
detected. The value **2** is not used in this document.

The final **Tool Confidence Level (TCL)** is calculated as follows: -
If **TI** is **1**, the **TCL** is also **1**, and no further actions
are required for tool qualification. - If **TI** is **2**, the highest
**TD** value among all linked, safety-relevant features and its errors is used to
determine the **TCL**.

A ``use case`` with a **TCL** of **2** or **3** requires special
handling during the tool qualification process.

.. list-table::
   :stub-columns: 1
   :header-rows: 1

   * - Type
     - Allowed values
     - Scope
     - Manually set?
   * - TI
     - 1, 2
     - use case
     - Yes
   * - TD
     - 1, 2, 3
     - error, feature
     - Yes
   * - TCL
     - 1, 2, 3
     - use case
     - Yes
