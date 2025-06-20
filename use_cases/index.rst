:octicon:`briefcase` Use cases
=================================

.. usecase:: Document software requirements
   :id: UC_SW_REQ
   :status: done
   :inputs: 
   :outputs:
   :tools: TOOL_SPHINX, TOOL_SPHINX-NEEDS, TOOL_UBC
   :features: 
      FE_SPHINX_READ, FE_SN_READ, FE_SN_CONTENT_RENDER, FE_SN_SET_META, FE_SN_LINK, FE_SN_TABLE,
      FE_SN_PIE, FE_SN_COUNT
   :ti: 2
   :ti_argu: Safety reasons
   :priority: 1
   :responsible:
   
   Create documentation to document and track software requirements.
   Input are ``rst`` files and output is a static website with ``HTML``, ``CSS`` and ``JS`` files.


   The documentation is used as part of an official release delivery. 

.. usecase:: Document SW architecture
   :id: UC_SW_ARCH
   :outputs: 
   :tools: TOOL_SPHINX, TOOL_SPHINX-NEEDS
   :features: 
   :ti: 2
   
   Create documentation to document and track software architecture.

   The documentation is used as part of an official release delivery. 

.. usecase:: Document SW Detail Design (SW API)
   :id: UC_SW_API
   :outputs: 
   :tools: TOOL_SPHINX, TOOL_SPHINX-NEEDS
   :features: 
   :ti: 2
   
   Create documentation to document and track software detailed design.

   The documentation is used as part of an official release delivery. 

.. usecase:: Document software qualification tests and results
   :id: UC_SW_QA
   :inputs: 
   :outputs:
   :tools: TOOL_SPHINX, TOOL_SPHINX-NEEDS
   :features: 
   :ti: 2
   
   Create documentation to document software qualification.

   The documentation is used as part of an official release delivery. 

.. usecase:: Document SW Unit test cases and results
   :id: UC_UNIT_TEST
   :outputs: 
   :tools: TOOL_SPHINX, TOOL_SPHINX-NEEDS
   :features: 
   :ti: 2
   
   Create documentation to document and track software  unit test cases.

   The documentation is used as part of an official release delivery. 