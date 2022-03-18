Usage
=====

Getting started with Potato is easy! Here are the 


Install Potato to your machine
---------------

Potato has a Python-based server architecture that can be run locally or hosted on any device. In order to install Potato: 

* Make sure you have Python version 3.0.0+ installed 
* Follow the quickstart instructions `here <https://potato-annotation-tutorial.readthedocs.io/en/latest/quick-start.html>`_.


Prepare your data
------------

Each document needs, at minimum, an :code:`id` field and a :code:`text` field. We support multiple formats of raw data files, including: csv, json, 


Create your schema
----------------

The schema includes: 

* Questions: you should have one or more questions for annotators to answer

  * Content: long text to display on the front end + short text for the header of the response file 
  * Annotation Type: ``multiselect`` (checkboxes), ``radio`` (single selection), ``likert`` (scale with endpoints labeled), ``text`` (free-form)
  * Other Features: 
  
    * ``required``
    * ``horizontal`` 
    * ``has_free_response`` (whether to include at the end of multiselect or radio question)
  
* Answers: except for ``text`` types, each question should have one or more answers

  * Content: 
  * Tooltip text: either 1) plain text or 2) for formatted tooltipcs, path to html file on the machine
  * `Keyboard shortcuts <https://potato-annotation-tutorial.readthedocs.io/en/latest/productivity.html#keyboard-shortcuts>`_: use keyboard instead of mouse to select and deselcet answers. There are two options:
  
    * Sequential Key Binding: automatically assign keys to each answer based on numeric order (i.e., first answer corresponds the '1' key, the second to the '2' key, etc.)
    * Custom Keypress Binding: specify which keys correspond to each answer, so they make logical sense to the annotator
  
  * `Keywords to highlight <https://potato-annotation-tutorial.readthedocs.io/en/latest/productivity.html#dynamic-highlighting>`_: 

Formatting the schema in the config 

* Basic examples are `here <https://potato-annotation-tutorial.readthedocs.io/en/latest/schemas_and_templates.html>`_
* Examples of the advanced productivity features like custom key bindings, keyword highlights, and active learning are `here <https://potato-annotation-tutorial.readthedocs.io/en/latest/productivity.html>`_


Choose (or create) your template
----------------

multi-select classification for text
single-select classification for text
rating text
rating gifs 
best-worst scaling for text
question-answering
multiple tasks

.. code-block:: yaml

    # The html that changes the visualiztation for your task. Change this file
    # to influence the layout and description of your task. This is not a full
    # HTML page, just the piece that does lays out your task's pieces
    "html_layout": "templates/examples/plain_layout.html",

    # The core UI files for Potato. You should not need to change these normally.
    #
    # Exceptions to this might include:
    # 1) You want to add custom CSS/fonts to style your task
    # 2) Your layout requires additional JS/assets to render
    # 3) You want to support additional keybinding magic
    #
    "base_html_template": "templates/base_template.html",
    "header_file": "templates/header.html",

    # This is where the actual HTML files will be generated. You should not need to change this normally.
    "site_dir": "potato/templates/",


The ``html_layout`` field can be set to one of the example templates `here <https://github.com/davidjurgens/potato/tree/master/templates/examples>`_ or to a custom template you specify:

* ``templates/examples/kwargs_example.html``: this template specifies the layout for Likert scales 
* ``templates/examples/plain_layout.html``: this template covers a wide range of NLP tasks (e.g., text classification, image or gif classification, best-worst scaling, question answering, multiple questions), and is designed to minimize scrolling and optimize placement of the document and questions on the screen.
* Custom: the templates can be easily customized using JINJA expressions to specify where parts of the annotation task and data are populated within the user-defined template.


Set up your YAML config file (optional)
---------------

To launch a Potato instance, the deployer first defines a YAML file that specifies the annotation schemes, data sources, server configuration, and any custom visualizations. Several examples  are given `here <https://github.com/davidjurgens/potato/tree/master/config/examples>_`.

If potato is launched without a YAML, the server will provide the deployer the option of following a series of prompts about their task to automatically generate a YAML file for them. A YAML file is then passed to the server on the command line to launch the server for annotation.


`active learning <https://potato-annotation-tutorial.readthedocs.io/en/latest/productivity.html#active-learning>`_

Launch potato locally
---------------


