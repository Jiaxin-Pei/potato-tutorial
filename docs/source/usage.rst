Usage
=====

Getting started with Potato is easy! Here are the 


Step 1: Install Potato to your machine
======================

Potato has a Python-based server architecture that can be run locally or hosted on any device. In order to install Potato: 
* Make sure you have Python version 3.0.0+ installed 
* Follow the quickstart instructions `here <https://potato-annotation-tutorial.readthedocs.io/en/latest/quick-start.html>`_.


Step 2: Set up your task
---------------

To launch a \potato instance, the deployer first defines a YAML file that specifies the annotation schemes, data sources, server configuration, and any custom visualizations. If \potato is launched without a YAML, the server will provide the deployer the option of following a series of prompts about their task to automatically generate a YAML file for them. A YAML file is then passed to the server on the command line to launch the server for annotation.

Several examples are given `here <https://github.com/davidjurgens/potato/tree/master/config/examples>_`.


Prepare your data
------------

Each document needs, at minimum, an :code:`id` field and a :code:`text` field. We support multiple formats of raw data files, including: csv, json, 


Create your schema
----------------

The schema includes: 
* Questions: you should have one or more questions for annotators to answer
  * Content:
  * Annotation Type: multiple-selection (checkboxes), ``radio`` (single selection), best-worst scaling, Likert scale, ``text`` (free-form)
  * Other Features: ``required``, 
* Answers: each question should have one or more anqers 
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


Example templates are `here <https://github.com/davidjurgens/potato/tree/master/templates>`_. These templates cover a wide range of NLP tasks and can be easily adapted. 
* ``text classification``
* ``image classification``
* ``Best-worst Scaling``


`active learning <https://potato-annotation-tutorial.readthedocs.io/en/latest/productivity.html#active-learning>`_

Step 3: Launch potato locally
======================


