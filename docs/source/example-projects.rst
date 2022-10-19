Example projects (project hub)
=====
Potato aims to improve the replicability of data annotation and reduce the cost for researchers to set up new annotation tasks. Therefore, Potato comes with a list of predefined example projects, and welcome public contribution to the project hub. If you have used potato for your own annotation, you are encouraged to create a pull request and release your annotation setup. 

Dialogue analysis (span + categorization)
------------

    [launch] python3 potato/flask_server.py example-projects/dialogue_analysis/configs/dialogue-analysis.yaml -p 8000
    [Annotate] http://localhost:8000

.. image:: ../img/dialogue_analysis.gif
   :width: 1000
   :alt: The log-in screen has an account creation button on the bottom right, circled in red.

Sentiment analysis (categorization)
------------

    [launch] python3 potato/flask_server.py example-projects/sentiment_analysis/configs/sentiment-analysis.yaml -p 8000
    [Annotate] http://localhost:8000
    
![plot](./images/sentiment_analysis.png)
    
Summarization evaluation (likert + categorization)
------------

    [launch] python3 potato/flask_server.py example-projects/summarization_evaluation/configs/summ-eval.yaml -p 8000
    [Annotate] http://localhost:8000/?PROLIFIC_PID=user
    
![plot](./images/summ_eval.png)

Match findings in papers and news (likert + prescreening questions + multi-task)
------------

    [Setup configuration files for multiple similar tasks] python3 potato/setup_multitask_config.py example-projects/match_finding/multitask_config.yaml
    [launch] python3 potato/flask_server.py example-projects/match_finding/configs/Computer_Science.yaml -p 8000
    [Annotate] http://localhost:8000/?PROLIFIC_PID=user
    
![plot](./images/match_finding.gif)
