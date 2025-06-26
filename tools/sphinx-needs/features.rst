Features
========

.. dropdown:: 🔍 Features

   .. needtable::
      :filter: "tools/sphinx-needs/" in docname and type == "feature"
      :columns: id, title, si as "SI", parent_needs_back as "Errors"

   .. needpie:: Sphinx-Needs features
      :legend:
      :labels: Safety impact, No impact, Undefined impact
      
      type == "feature" and "tools/sphinx-needs/" in docname and si == "yes"
      type == "feature" and "tools/sphinx-needs/" in docname and si == "no"
      type == "feature" and "tools/sphinx-needs/" in docname and si == ""

.. feature:: Read Traceability objects in Sphinx-Needs
   :id: FE_SN_READ
   :tools: TOOL_SN
   :si: yes

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
   :tools: TOOL_SN
   :si: yes

   .. error:: Content contains syntax errors
      :id: ER_SN_CONTENT_SYNTAX
      :td: 1

.. feature:: Assign meta-data to Traceability objects in Sphinx-Needs
   :id: FE_SN_SET_META
   :tools: TOOL_SN
   :si: yes

   .. error:: Dynamic functions return invalid meta-data
      :id: ER_SN_DYN_INVALID
      :td: 1

   .. error:: Dynamic functions return wrong meta-data
      :id: ER_SN_DYN_WRONG
      :td: 3

      Internal dynamic functions are checked by test-cases in Sphinx-Needs
      itself.

      But self-written dynamic functions can do whatever they want, as long
      as the returned data ist still valid (but may be wrong).

      So self-written dynamic functions need test cases as well!

   .. error:: Sphinx-Needs data not valid
      :id: ER_SN_META_INVALID
      :td: 1

   .. error:: Sphinx-Needs data is not process-compliant
      :id: ER_SN_META_NOT_COMPLIANT
      :td: 1

.. feature:: Establish links between Traceability objects in Sphinx-Needs
   :id: FE_SN_LINK
   :tools: TOOL_SN
   :si: yes

   .. error:: Back-links are not set
      :id: ER_SN_LINKS_NO_BACK
      :td: 1

      Links are set only in one direction but not in the other.

      This may lead to missing information, e.g. a Traceability object is
      linked to a specification, but you can't find the linked Traceability
      object during specification implementation.

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

      Set links are not treated correctly and are not part of the final
      documentation.

      Sphinx-Needs shows a warning for all not found used need-IDs for
      links.

.. feature:: Generate object representation in Sphinx-Needs
   :id: FE_SN_DOCTREE
   :tools: TOOL_SN
   :si: yes

   .. error:: Meta-data missing
      :id: ER_SN_LAY_META_MIS
      :td: 1

      Needed meta-data is not part of the final representation in the
      doctree and so later HTML/PDF build

   .. error:: Wrong meta-data is used
      :id: ER_SN_LAY_META_WRONG
      :td: 1

      Sphinx-Needs is adding wrong Meta-Data to the final doctree-layout

.. feature:: Export needs.json file using Sphinx-Needs
   :id: FE_SN_JSON
   :tools: TOOL_SN
   :si: yes

   .. error:: Objects missing in needs.json
      :id: ER_SN_JSON_MIS
      :td: 1

   .. error:: Traceability objects meta-data corrupted
      :id: ER_SN_JSON_COR
      :td: 1

Dynamic Content
+++++++++++++++

.. feature:: Apply dynamic functions for meta-data computation
   :id: FE_SN_DYN_FUNC
   :tools: TOOL_SN
   :si: yes

   .. error:: Function gets not executed
      :id: ER_SN_DYN_NO_EXEC
      :td: 1

      The function gets not executed and in the generated documentation the
      dynamic-function string can be found.

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
   :tools: TOOL_SN
   :si: yes

.. feature:: Enhance Need content using templates in Sphinx-Needs
   :id: FE_SN_TEMPLATE_NEED
   :tools: TOOL_SN
   :si: yes

Core Need Object
++++++++++++++++

.. feature:: Definable need types
   :id: FE_SPHINX_NEEDS_DEFINABLE_TYPES
   :tools: TOOL_SN
   :si: yes

   Allows the definition of custom need types beyond the built-in ones.
   Each type gets its own directive, title, and color for easy
   identification in diagrams.

   .. code-block:: python

      # In conf.py
      needs_types = [
          dict(directive="req", title="Requirement", prefix="R_", color="#BFD8D2"),
          dict(directive="spec", title="Specification", prefix="S_", color="#FEDCD2"),
          dict(directive="test", title,"Test Case", prefix="T_", color="#DCFED2"),
      ]

.. feature:: Customizable need options
   :id: FE_SPHINX_NEEDS_CUSTOMIZABLE_OPTIONS
   :tools: TOOL_SN
   :si: yes

   Define extra options that any need object can have, such as 'author'
   or 'component'. These custom options can be displayed in tables and
   used for filtering.

   .. code-block:: python

      # In conf.py
      needs_extra_options = ['author', 'component']

   .. code-block:: rst

      .. req:: A specific requirement
         :id: R_001
         :author: John Doe
         :component: UI

.. feature:: Customizable link types
   :id: FE_SPHINX_NEEDS_CUSTOMIZABLE_LINKS
   :tools: TOOL_SN
   :si: yes

   Define different types of links between needs to represent various
   relationships. This helps to create a precise traceability model.

   .. code-block:: python

      # In conf.py
      needs_extra_links = [
          {
              "option": "verifies",
              "incoming": "verified by",
              "outgoing": "verifies",
          },
          {
              "option": "implements",
              "incoming": "implemented by",
              "outgoing": "implements",
          }
      ]

.. feature:: Automatic ID generation
   :id: FE_SPHINX_NEEDS_AUTO_ID
   :tools: TOOL_SN
   :si: yes

   Sphinx-Needs can automatically generate a unique ID for any need that
   does not have one. The format of the ID can be configured using a
   prefix and a specific length.

   .. code-block:: rst

      .. req:: This requirement will get an ID automatically.
         :tags: auto_id

.. feature:: Manual ID assignment
   :id: FE_SPHINX_NEEDS_MANUAL_ID
   :tools: TOOL_SN
   :si: yes

   Allows for setting a specific, human-readable ID for a need. This is
   useful for referencing important requirements easily.

   .. code-block:: rst

      .. req:: A requirement with a specific ID
         :id: R_IMPORTANT_FEATURE

.. feature:: Need status enforcement
   :id: FE_SPHINX_NEEDS_STATUS_ENFORCEMENT
   :tools: TOOL_SN
   :si: yes

   You can define a list of allowed statuses for needs. If a need uses a
   status that is not on the list, Sphinx will raise a warning during the
   build.

   .. code-block:: python

      # In conf.py
      needs_statuses = [
          ('open', 'Is still open'),
          ('in_progress', 'Work in progress'),
          ('closed', 'Is closed'),
          ('rejected', 'Will not be implemented'),
      ]

.. feature:: Tagging support
   :id: FE_SPHINX_NEEDS_TAGGING
   :tools: TOOL_SN
   :si: yes

   Assign one or more tags to a need for categorization and filtering.
   Tags help in organizing needs and creating specific views or reports.

   .. code-block:: rst

      .. spec:: A specification for the login system
         :id: S_LOGIN
         :tags: ui, security

.. feature:: In-content need parts for granular references
   :id: FE_SPHINX_NEEDS_NEED_PARTS
   :tools: TOOL_SN
   :si: yes

   Create references to specific sentences or parts inside a need's
   content. This allows for very precise linking and traceability.

   .. code-block:: rst

      .. req:: User Authentication
         :id: R_AUTH

         The user must be able to log in via a username and password.
         The password must be stored securely. :np:`secure_storage`

      .. test:: Test secure password storage
         :id: T_SECURE_STORAGE
         :links: R_AUTH.secure_storage

.. feature:: Unique ID enforcement and checks
   :id: FE_SPHINX_NEEDS_UNIQUE_ID_ENFORCEMENT
   :tools: TOOL_SN
   :si: yes

   Sphinx-Needs automatically checks if all manually set IDs are unique
   across the project. The build will fail if a duplicate ID is found,
   ensuring data consistency.

Directives for Creating & Displaying Needs
++++++++++++++++++++++++++++++++++++++++++

.. feature:: Display needs in a filterable table (needtable)
   :id: FE_SPHINX_NEEDS_DIRECTIVE_NEEDTABLE
   :tools: TOOL_SN
   :si: no

   Renders a table of needs based on specified filters. The table columns
   can be customized to show different need options like status or
   outgoing links.

   .. code-block:: rst

      .. needtable::
         :tags: ui
         :status: open
         :columns: id, title, status, links

.. feature:: Render a PlantUML flow diagram of needs (needflow)
   :id: FE_SPHINX_NEEDS_DIRECTIVE_NEEDFLOW
   :tools: TOOL_SN
   :si: no

   Generates a flowchart that visualizes the relationships between
   filtered needs. This is excellent for showing process flows or
   dependencies.

   .. code-block:: rst

      .. needflow::
         :tags: login_flow
         :show_legend:

.. feature:: Create a pie chart based on need statistics (needpie)
   :id: FE_SPHINX_NEEDS_DIRECTIVE_NEEDPIE
   :tools: TOOL_SN
   :si: no

   Generates a pie chart from need data, for instance, to show the
   distribution of statuses. This provides a quick visual summary of the
   project's state.

   .. code-block:: rst

      .. needpie:: Requirements Status
         :content: status
         :legend:

.. feature:: Create a bar chart based on need statistics (needbar)
   :id: FE_SPHINX_NEEDS_DIRECTIVE_NEEDBAR
   :tools: TOOL_SN
   :si: no

   Generates a bar chart to visualize need data. This is useful for
   comparing counts across different categories, such as components.

   .. code-block:: rst

      .. needbar:: Needs per Component
         :x_option: component
         :x_labels: UI, Backend, Database

.. feature:: Import needs from an external JSON file (needimport)
   :id: FE_SPHINX_NEEDS_DIRECTIVE_NEEDIMPORT
   :tools: TOOL_SN
   :si: yes

   Import need objects from an external ``needs.json`` file. This allows
   for sharing and reusing requirements across different Sphinx projects.

   .. code-block:: rst

      .. needimport:: ../../shared/output/needs.json

.. feature:: Modify existing needs in bulk (needextend)
   :id: FE_SPHINX_NEEDS_DIRECTIVE_NEEDEXTEND
   :tools: TOOL_SN
   :si: yes

   Modifies multiple needs at once based on a filter. You can add tags,
   change the status, or set any other option for all filtered needs.

   .. code-block:: rst

      .. needextend:: status == 'in_progress'
         :add_tags: sprint_5

Linking and Traceability
++++++++++++++++++++++++

.. feature:: Direct linking between needs using IDs
   :id: FE_SPHINX_NEEDS_LINKING_DIRECT
   :tools: TOOL_SN
   :si: yes

   Create links between needs by referencing their unique IDs in link
   options. This forms the basis of all traceability in Sphinx-Needs.

   .. code-block:: rst

      .. spec:: Defines how the login button works.
         :id: S_LOGIN_BUTTON

      .. req:: The login button must be blue.
         :id: R_LOGIN_COLOR
         :links: S_LOGIN_BUTTON

.. feature:: Bidirectional link tracking
   :id: FE_SPHINX_NEEDS_LINKING_BIDIRECTIONAL
   :tools: TOOL_SN
   :si: yes

   When you link from need A to need B, Sphinx-Needs automatically knows
   about the incoming link on need B. This allows for full, bidirectional
   traceability without extra work.

.. feature:: Dead link detection and warnings
   :id: FE_SPHINX_NEEDS_LINKING_DEAD_LINK_DETECTION
   :tools: TOOL_SN
   :si: yes

   The Sphinx build will issue a warning if a need links to an ID that
   does not exist. This helps to maintain the integrity of the
   traceability data.

Automated Features
++++++++++++++++++

.. feature:: Constraint checking to validate need relationships
   :id: FE_SPHINX_NEEDS_DYNAMIC_CONSTRAINTS
   :tools: TOOL_SN
   :si: yes

   Define rules, or constraints, about your need data that are checked
   during the build. For example, you can enforce that every requirement
   must be linked to a test case.

   .. code-block:: python

      # In conf.py
      needs_constraints = {
          "req_verified": {
              "check_code": "len(links_back['verifies']) > 0",
              "severity": "error",
              "filter": "'req' in tags"
          }
      }

Configuration & Customization
+++++++++++++++++++++++++++++

.. feature:: Configuration via conf.py or an external TOML file
   :id: FE_SPHINX_NEEDS_CONFIG_FILES
   :tools: TOOL_SN
   :si: no

   All Sphinx-Needs options can be configured in the main ``conf.py`` file.
   For large configurations, you can also use an external ``needs.toml``
   file to keep things organized.

.. feature:: Customizable layouts for need presentation
   :id: FE_SPHINX_NEEDS_CONFIG_LAYOUTS
   :tools: TOOL_SN
   :si: yes

   Change the visual presentation of needs by defining custom layouts.
   You can reorder options, use grids, and change how information is
   displayed.

   .. code-block:: python

      # In conf.py
      needs_layouts = {
          'my_layout': {
              'grid': 'simple_side_right',
              'layout': {
                  'side': ['id', 'status', 'tags', 'links']
              }
          }
      }

Exporting & Reporting
+++++++++++++++++++++

.. feature:: JSON builder to export all need data
   :id: FE_SPHINX_NEEDS_EXPORT_JSON
   :tools: TOOL_SN
   :si: yes

   Export all need objects and their relationships into a structured ``needs.json``
   file. This file can be used for external analysis, reporting, or
   imported into other Sphinx projects.

   .. code-block:: bash

      sphinx-build -b needs . _build

.. feature:: Permalink generation to specific need objects
   :id: FE_SPHINX_NEEDS_EXPORT_PERMALINKS
   :tools: TOOL_SN
   :si: yes

   Generate a ``needs.json`` file where each need includes a permalink to
   its location in the HTML documentation. This is useful for linking
   from external tools directly to the requirement definition.
