Usage
=====

Getting started with Potato is easy! Here's what you need to do:


Install Potato to your machine
---------------

Potato has a Python-based server architecture that can be run locally or hosted on any device. In order to install Potato: 

* Make sure you have Python version 3 installed 
* Follow the quickstart instructions `here <https://potato-annotation-tutorial.readthedocs.io/en/latest/quick-start.html>`_.


Set up the project data
------------

* `Prepare <>`_ your input data (csv, tsv, or json) and upload it in the ``data`` folder
* Set up the format  `specifications <>`_ in the YAML file
* Update the config YAML file with `input <>`_ and `output <>`_ data preferences


Create your codebook and schema
----------------

* Create your annotation codebook and `link it <https://potato-annotation-tutorial.readthedocs.io/en/latest/schemas_and_templates.html>`_ to the annotation interface
* Specify the `schema <>`_, including:

    * Annotation Type: ``multiselect`` (checkboxes), ``radio`` (single selection), ``likert`` (scale with endpoints labeled), or ``text`` (free-form)
    * Questions for annotators 
    * Answer Choices for multiselect and radio types 
    * Likert Scale length and end labels for likert type questions
    * Optional Question Features: ``required``, ``horizontal`` (placement of answers are horizontal not vertical), ``has_free_response`` (whether to include an open text box at the end of multiselect or radio question, like having an "other" option)
    * Optional Answer Features: `tooltips <>`_, `keyboard shortcuts <https://potato-annotation-tutorial.readthedocs.io/en/latest/productivity.html#keyboard-shortcuts>`_, `keywords to highlight <https://potato-annotation-tutorial.readthedocs.io/en/latest/productivity.html#dynamic-highlighting>`_

* Format the schema for the YAML config file (`basic examples <https://potato-annotation-tutorial.readthedocs.io/en/latest/schemas_and_templates.html>`_ and `advanced examples <https://potato-annotation-tutorial.readthedocs.io/en/latest/productivity.html>`_)



Define annotation settings
----------------

* Choose an existing html template for the annotation task or create a new one
* Optionally, set up `active learning <https://potato-annotation-tutorial.readthedocs.io/en/latest/productivity.html#active-learning>`_
* Update the YAML file with these settings


Launch potato locally
---------------

And that's it! You can go ahead and get started labeling data in one of two ways:

**Option 1:** Follow the prompts given above to define a YAML file that specifies the data sources, server configuration, annotation schemes, and any custom visualizations (`examples <https://github.com/davidjurgens/potato/tree/master/config/examples>_`) and then launch potato; or

**Option 2:** Launch potato without a YAML. In this case, the server will have you follow a series of prompts about the task and automatically generate a YAML file for you. A YAML file is then passed to the server on the command line to launch the server for annotation.



