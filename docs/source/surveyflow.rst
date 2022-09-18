Surveyflow
=====

Potato allows you to easily set up a series of modules traditionally used in social science surveys.


Pre-study survey
---------------
You could easily insert any survey questions using our built-in schemas: likert, radio, checkbox, textbox, drop-down list. 
Potato also provide templates for setting up task instructions and user consents. 

Step 1, prepare a .jsonl file for the survey questions you want to insert. For example, if you want to insert a page of censent questions, you can add the following likes to a jsonl file named consent.jsonl

.. code-block:: YAML

        {"id":"1","text":"I certify that I am at least 18 years of age.","schema": "radio", "choices": ["I agree", "I disagree"], "label_requirement": {"right_label":["I agree"]}}
        {"id":"2","text":"I have read and understood the information above.","schema": "radio", "choices": ["Yes", "No"], "label_requirement": {"right_label":["Yes"]}}
        {"id":"3","text":"I understand I might see potentially offensive or sexual content.","schema": "radio", "choices": ["Yes", "No"], "label_requirement": {"right_label":["Yes"]}}
        {"id":"4","text":"I want to participate in this research and continue with the study.","schema": "radio", "choices": ["Yes", "No"], "label_requirement": {"right_label":["Yes"]}}

Step 2, insert the file path into the configuration file:
.. code-block:: YAML

        "surveyflow": {
                "on": true,
                "order": [
                    "pre_annotation",
                    "post_annotation"
                ],
                "pre_annotation": [
                    "projects/your-project-name/surveyflow/English/consent.jsonl",
                ],
                "post_annotation": [
                ],
            },

Potato will automatically create a consent page for all the annotators when you launch it.

Pre-study test
---------------



Attention test
---------------



Post-study survey
---------------



Built-in demographic questions
---------------
