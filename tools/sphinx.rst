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

   Features without errors: :need_count:`"Sphinx" in sections and type == "feature" and len(parent_needs_back) == 0`
   / :need_count:`"Sphinx" in sections and type == "feature"`

   Errors without a mitigation: :need_count:`"Sphinx" in sections and type == "error" and (len(avoids_back) == 0 and len(checks_back) == 0)`
   / :need_count:`"Sphinx" in sections and type == "error"`

   Restrictions without error: :need_count:`"Sphinx" in sections and type == "restriction" and len(avoids) == 0`
   / :need_count:`"Sphinx" in sections and type == "restriction"`

   Checks without error: :need_count:`"Sphinx" in sections and type == "check" and len(checks) == 0`
   / :need_count:`"Sphinx" in sections and type == "check"`

Features
--------

.. feature:: Read-in documents with Sphinx
   :id: FE_SPHINX_READ
   :tools: TOOL_SPHINX

   Readin all needed rst/md files for the Sphinx project.

   .. error:: Needed folders/files are ignored
      :id: ER_FILES_IGNORED
      :td: 1

      Error is logged by Sphinx and with build-option ``-W`` this warning
      gets thrown as error and stops the build.

   .. error:: Needed files/folders have not supported encoding
      :id: ER_SPH_WRONG_ENCODING
      :td: 1

   .. error:: Access to files/folders not given
      :id: ER_SPH_WRONG_ACCESS
      :td: 1

Inline Text Formatting
++++++++++++++++++++++

.. feature:: Italicized (Emphasis) Text
   :id: FE_SPHINX_INLINE_EMPHASIS
   :tools: TOOL_SPHINX

   Use emphasis to italicize text in your documentation.

   .. code-block:: rst

      This is *italicized* text.

.. feature:: Bold (Strong) Text
   :id: FE_SPHINX_INLINE_STRONG
   :tools: TOOL_SPHINX

   Use strong emphasis to make text bold.

   .. code-block:: rst

      This is **bold** text.

.. feature:: Inline Literal (Code) Text
   :id: FE_SPHINX_INLINE_LITERAL
   :tools: TOOL_SPHINX

   Use inline literals to display code or commands inline.

   .. code-block:: rst

      This is ``inline code``.

.. feature:: Named Hyperlink Reference
   :id: FE_SPHINX_INLINE_NAMED_HYPERLINK
   :tools: TOOL_SPHINX

   Create a named hyperlink reference to link to external or internal resources.

   .. code-block:: rst

      `Sphinx Documentation <https://www.sphinx-doc.org/en/master/>`__

.. feature:: Inline Internal Target
   :id: FE_SPHINX_INLINE_INTERNAL_TARGET
   :tools: TOOL_SPHINX

   Use internal targets to create cross-references within your documentation.

   .. code-block:: rst

      See :ref:`example-section` for more details.

.. feature:: Escaped Markup Characters
   :id: FE_SPHINX_INLINE_ESCAPE
   :tools: TOOL_SPHINX

   Escape special characters to display them as plain text.

   .. code-block:: rst

      Use \\* to display an asterisk (*).

.. feature:: Subscript Role
   :id: FE_SPHINX_ROLE_SUBSCRIPT
   :tools: TOOL_SPHINX

   Use the subscript role to display text as a subscript.

   .. code-block:: rst

      H\ :sub:`2`\ O

.. feature:: Superscript Role
   :id: FE_SPHINX_ROLE_SUPERSCRIPT
   :tools: TOOL_SPHINX

   Use the superscript role to display text as a superscript.

   .. code-block:: rst

      E = mc\ :sup:`2`

.. feature:: Strong Role
   :id: FE_SPHINX_ROLE_STRONG
   :tools: TOOL_SPHINX

   Use the strong role to emphasize text strongly.

   .. code-block:: rst

      :strong:`Important!`

.. feature:: Emphasis Role
   :id: FE_SPHINX_ROLE_EMPHASIS
   :tools: TOOL_SPHINX

   Use the emphasis role to italicize text.

   .. code-block:: rst

      :emphasis:`This is emphasized text.`

.. feature:: Literal Role
   :id: FE_SPHINX_ROLE_LITERAL
   :tools: TOOL_SPHINX

   Use the literal role to display inline code or commands.

   .. code-block:: rst

      :literal:`print("Hello, World!")`

.. feature:: Code Role
   :id: FE_SPHINX_ROLE_CODE
   :tools: TOOL_SPHINX

   Use the code role to highlight inline code snippets.

   .. code-block:: rst

      :code:`def example(): pass`

.. feature:: Inline Math Role
   :id: FE_SPHINX_ROLE_MATH
   :tools: TOOL_SPHINX

   Use the math role to display inline mathematical expressions.

   .. code-block:: rst

      :math:`E = mc^2`

Structural Elements
+++++++++++++++++++

.. feature:: Section Titles with Underlines
   :id: FE_SPHINX_STRUCTURE_SECTION_TITLES
   :tools: TOOL_SPHINX

.. feature:: Document Title and Subtitle
   :id: FE_SPHINX_STRUCTURE_DOC_TITLE
   :tools: TOOL_SPHINX

.. feature:: Transitions (Horizontal Lines)
   :id: FE_SPHINX_STRUCTURE_TRANSITIONS
   :tools: TOOL_SPHINX

.. feature:: Table of Contents Tree Directive (toctree)
   :id: FE_SPHINX_DIRECTIVE_TOCTREE
   :tools: TOOL_SPHINX

.. feature:: Rubric Directive
   :id: FE_SPHINX_DIRECTIVE_RUBRIC
   :tools: TOOL_SPHINX

Lists and Quotes
++++++++++++++++

.. feature:: Bulleted Lists
   :id: FE_SPHINX_LISTS_BULLETED
   :tools: TOOL_SPHINX

.. feature:: Numbered (Enumerated) Lists
   :id: FE_SPHINX_LISTS_ENUMERATED
   :tools: TOOL_SPHINX

.. feature:: Auto-Numbered Lists
   :id: FE_SPHINX_LISTS_AUTO_NUMBERED
   :tools: TOOL_SPHINX

.. feature:: Nested Lists
   :id: FE_SPHINX_LISTS_NESTED
   :tools: TOOL_SPHINX

.. feature:: Definition Lists
   :id: FE_SPHINX_LISTS_DEFINITION
   :tools: TOOL_SPHINX

.. feature:: Option Lists
   :id: FE_SPHINX_LISTS_OPTION
   :tools: TOOL_SPHINX

.. feature:: Block Quotes
   :id: FE_SPHINX_CONTENT_BLOCKQUOTES
   :tools: TOOL_SPHINX

.. feature:: Line Blocks
   :id: FE_SPHINX_CONTENT_LINE_BLOCKS
   :tools: TOOL_SPHINX

Directives for Content
++++++++++++++++++++++

.. feature:: Image Directive
   :id: FE_SPHINX_DIRECTIVE_IMAGE
   :tools: TOOL_SPHINX

.. feature:: Figure Directive
   :id: FE_SPHINX_DIRECTIVE_FIGURE
   :tools: TOOL_SPHINX

.. feature:: Table Directive with Title
   :id: FE_SPHINX_DIRECTIVE_TABLE
   :tools: TOOL_SPHINX

.. feature:: Simple Tables
   :id: FE_SPHINX_TABLES_SIMPLE
   :tools: TOOL_SPHINX

.. feature:: Grid Tables
   :id: FE_SPHINX_TABLES_GRID
   :tools: TOOL_SPHINX

.. feature:: CSV Table Directive
   :id: FE_SPHINX_DIRECTIVE_CSV_TABLE
   :tools: TOOL_SPHINX

.. feature:: List Table Directive
   :id: FE_SPHINX_DIRECTIVE_LIST_TABLE
   :tools: TOOL_SPHINX

.. feature:: Code Block Directive
   :id: FE_SPHINX_DIRECTIVE_CODE_BLOCK
   :tools: TOOL_SPHINX

.. feature:: Literal Include Directive
   :id: FE_SPHINX_DIRECTIVE_LITERALINCLUDE
   :tools: TOOL_SPHINX

.. feature:: Math Directive
   :id: FE_SPHINX_DIRECTIVE_MATH
   :tools: TOOL_SPHINX

.. feature:: Contents Directive (Local ToC)
   :id: FE_SPHINX_DIRECTIVE_CONTENTS
   :tools: TOOL_SPHINX

.. feature:: Include Directive
   :id: FE_SPHINX_DIRECTIVE_INCLUDE
   :tools: TOOL_SPHINX

.. feature:: Raw Content Directive
   :id: FE_SPHINX_DIRECTIVE_RAW
   :tools: TOOL_SPHINX

Directives for Admonitions
++++++++++++++++++++++++++

.. feature:: Note Admonition
   :id: FE_SPHINX_ADMONITION_NOTE
   :tools: TOOL_SPHINX

.. feature:: Warning Admonition
   :id: FE_SPHINX_ADMONITION_WARNING
   :tools: TOOL_SPHINX

.. feature:: Hint Admonition
   :id: FE_SPHINX_ADMONITION_HINT
   :tools: TOOL_SPHINX

.. feature:: Tip Admonition
   :id: FE_SPHINX_ADMONITION_TIP
   :tools: TOOL_SPHINX

.. feature:: Important Admonition
   :id: FE_SPHINX_ADMONITION_IMPORTANT
   :tools: TOOL_SPHINX

.. feature:: Attention Admonition
   :id: FE_SPHINX_ADMONITION_ATTENTION
   :tools: TOOL_SPHINX

.. feature:: Caution Admonition
   :id: FE_SPHINX_ADMONITION_CAUTION
   :tools: TOOL_SPHINX

.. feature:: Error Admonition
   :id: FE_SPHINX_ADMONITION_ERROR
   :tools: TOOL_SPHINX

.. feature:: Danger Admonition
   :id: FE_SPHINX_ADMONITION_DANGER
   :tools: TOOL_SPHINX

.. feature:: Generic Admonition
   :id: FE_SPHINX_ADMONITION_GENERIC
   :tools: TOOL_SPHINX

Hyperlinks and Cross-Referencing
++++++++++++++++++++++++++++++++

.. feature:: External Hyperlinks
   :id: FE_SPHINX_LINK_EXTERNAL
   :tools: TOOL_SPHINX

.. feature:: Implicit Hyperlinks from URLs
   :id: FE_SPHINX_LINK_IMPLICIT
   :tools: TOOL_SPHINX

.. feature:: Internal Cross-References to Labels
   :id: FE_SPHINX_LINK_INTERNAL_LABELS
   :tools: TOOL_SPHINX

.. feature:: Explicit Target Creation
   :id: FE_SPHINX_LINK_EXPLICIT_TARGET
   :tools: TOOL_SPHINX

.. feature:: Reference Role
   :id: FE_SPHINX_ROLE_REF
   :tools: TOOL_SPHINX

.. feature:: Document Role
   :id: FE_SPHINX_ROLE_DOC
   :tools: TOOL_SPHINX

.. feature:: Numbered Reference Role
   :id: FE_SPHINX_ROLE_NUMREF
   :tools: TOOL_SPHINX

.. feature:: Footnotes
   :id: FE_SPHINX_LINK_FOOTNOTES
   :tools: TOOL_SPHINX

.. feature:: Citations
   :id: FE_SPHINX_LINK_CITATIONS
   :tools: TOOL_SPHINX

Output and Build System
+++++++++++++++++++++++

.. feature:: HTML Output
   :id: FE_SPHINX_OUTPUT_HTML
   :tools: TOOL_SPHINX

.. feature:: Single-File HTML Output
   :id: FE_SPHINX_OUTPUT_SINGLE_HTML
   :tools: TOOL_SPHINX

.. feature:: Directory HTML Output
   :id: FE_SPHINX_OUTPUT_DIR_HTML
   :tools: TOOL_SPHINX

.. feature:: LaTeX Output
   :id: FE_SPHINX_OUTPUT_LATEX
   :tools: TOOL_SPHINX

.. feature:: ePub 3 Output
   :id: FE_SPHINX_OUTPUT_EPUB
   :tools: TOOL_SPHINX

.. feature:: Man Page Output
   :id: FE_SPHINX_OUTPUT_MANPAGE
   :tools: TOOL_SPHINX

.. feature:: Plain Text Output
   :id: FE_SPHINX_OUTPUT_TEXT
   :tools: TOOL_SPHINX

.. feature:: JSON Output
   :id: FE_SPHINX_OUTPUT_JSON
   :tools: TOOL_SPHINX

.. feature:: Gettext Message Catalog Output
   :id: FE_SPHINX_OUTPUT_GETTEXT
   :tools: TOOL_SPHINX

.. feature:: Built-in HTML Search
   :id: FE_SPHINX_BUILD_HTML_SEARCH
   :tools: TOOL_SPHINX

.. feature:: HTML Theming Support
   :id: FE_SPHINX_BUILD_THEMING
   :tools: TOOL_SPHINX

.. feature:: Static File Support
   :id: FE_SPHINX_BUILD_STATIC_FILES
   :tools: TOOL_SPHINX

Restrictions
------------

.. restriction:: Warning to Error
   :id: RE_SPHINX_WARNINGS
   :avoids: ER_FILES_IGNORED, ER_SPH_WRONG_ENCODING, ER_SPH_WRONG_ACCESS

   Always use the sphinx-build option ``-W`` to transform all warnings
   into errors, because only errors stop the build and set an exit code >
   0.

.. restriction:: Clean full build
   :id: RE_SPHINX_CLEAN

   Always use a **clean** and **full** sphinx-build. An incremental build
   is not allowed, as not all files get updated by Sphinx.

   So before the ``sphinx-build`` command gets executed, the related ``build``
   folder shall be deleted. Then ``sphinx-build`` shall be built with the
   options ``-a`` and ``-E`` to force Sphinx to read and write really all
   files.

Artifacts
---------

.. artifact:: rst file
   :id: ART_SPHINX_RST

   A rst (reStructuredText) file, which contains part of the overall
   documentation.
