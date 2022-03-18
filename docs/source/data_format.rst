Data Formats
=====


Prepare your input data
------------

Upload one or more files containing documents to be annotated in the ``data`` folder. 

We support multiple formats of raw data files, including: csv, tsv, json, or jsonl. 

Each document needs, at minimum, a unique identifier and the body of the document. 

You can find example data files `here <https://github.com/davidjurgens/potato/blob/master/data/>`_. We currently support four different document formats:

* Text: body is the document plaintext (`example <https://github.com/davidjurgens/potato/blob/master/data/toy-example.json>`_)
* Image, Video, or GIF: body is the filepath (`example <https://github.com/davidjurgens/potato/blob/master/data/video-label-example.json>`_)
* Best-Worst Scaling: body is a comma-separated list of documents to order (`example <https://github.com/davidjurgens/potato/blob/master/data/bws-example.json>`_)
* Likert Scaling with custom end points: body is one of the above + extra ``kwargs`` and ``other_kwargs`` fields for the  (`example <https://github.com/davidjurgens/potato/blob/master/data/bws-example.json>`_)
* Contextual Annotation: body is one of the above + extra ``context``  (`example <https://github.com/davidjurgens/potato/blob/master/data/>`_)




Update input data formats on the YAML config file 
-------------

You would pass the input data paths and field names into the YAML config file as follows: 

.. code-block:: yaml

    # Pass in a comma-separated list of data files containing documents to be annotated in this task
    "data_files": [
       "data/toy-example1.json",
       "data/toy-example2.json"
    ],

    # Specify the field names containing the document unique identifier (id) and document body (text)
    "item_properties": {
        "id_key": "id",
        "text_key": "text"
    },



Update output data preferences on the YAML config file 
------------

The output file will include each labeled document's id and annotations; the header will consist of the question and answer labels specified in the `schema <https://potato-annotation-tutorial.readthedocs.io/en/latest/schemas_and_templates.html>`_. You need to specify a subdirectory of the ``annotation_output`` directory where files for each annotator should be placed. We support multiple output formats, including: csv, tsv, json, or jsonl.

.. code-block:: yaml

    # Potato will write the annotation file for all annotations to this
    # directory, as well as per-annotator output files and state information
    # necessary to restart annotation.
    "output_annotation_dir": "annotation_output/folder_name/",

    # The output format for the all-annotator data. Allowed formats are:
    # * jsonl
    # * json (same output as jsonl)
    # * csv
    # * tsv
    #
    "output_annotation_format": "json", 


