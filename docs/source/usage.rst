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
* Question: 
** Content:
** Type: multiple-selection (checkboxes), single-selection (radio buttons), best-worst scaling, Likert scale, free-form text
** Other Features: required, 
* Answer
** Content: 
** Tooltip text: either 1) plain text or 2) for formatted tooltipcs, path to html file on the machine
* Keyboard shortcuts: 
* Keyword highlights: 

Formatting the schema in the config 
* Basic examples are `here <https://potato-annotation-tutorial.readthedocs.io/en/latest/schemas_and_templates.html>`_
* Examples of the advanced productivity features like custom key bindings, keyword highlights, and active learning are `here <https://potato-annotation-tutorial.readthedocs.io/en/latest/productivity.html>`_


Choose (or create) your template
----------------

\potato has been deployed in a variety of annotation settings over a two-year period, including a 27-class annotation scheme for immigration framing \cite{mendelsohn2021modeling}, rating condolences and empathy for Reddit comments with hundreds of words \cite{zhou2020condolences}, best-worst scaling for rating intimacy in questions \cite{pei2020quantifying}, rating Reddit threads for their prosociality conversations \cite{bao2021conversations}, Likert-scale rating sentences for scientific uncertainty \cite{pei2021measuring}, and rating the appropriateness of gif replies to messages, which showed animated gif in the interface \cite{wang2021animated}. 

Example templates are `here <https://github.com/davidjurgens/potato/tree/master/templates>`_. These templates cover a wide range of NLP tasks and can be easily adapted. 
* ``text classification``
* ``image classification``
* ``Best-worst Scaling``


Step 3: Launch potato locally
======================


