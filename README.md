kaggle_quora
==============================

Kaggle [Quora Insincere Question Classification](https://www.kaggle.com/c/quora-insincere-questions-classification) competition. This goal of this competition is to identify questions that are "toxic" in order to "combat trolls at scale". Specifically looking to identify questions that are non-neutral in tone, inflammatory / discriminatory in nature, based on false information or sexually shocking.

My intention for this project is to acquaint myself with text mining and natural language processing in Python. In particular I'm interested in learning more about: 
1. standard packages like NLTK
1. best practices in text pre-processing
1. do some gentle topic modeling and sentiment analysis
1. revisit the "classical" methods of text classification that I haven't looked at in a while (e.g. TF-IDF Naive-Bayes, etc)
1. learn a little about modern deep learning based text classification models using Keras w/ TensorFlow backend.

## Progress

### [Step 0: EDA](notebooks/0_EDA.ipynb)

Starting with some exploration of the training set. Using intuition or research guided, investigated whether some certain topics / terms had higher or lower insincerity rates than the base-rate. Considered engineered features such as word-count, character-count, question structure (e.g. leading Why vs How / Which / What?), whether the question appeared to contained math or equations, and finally whether the question contained the names of the most popular programming languages / frameworks / IDEs listed on the [Stack Overflow Developer Survey 2018](https://insights.stackoverflow.com/survey/2018/).

The main take aways: 
* intuitions generally proved correct (e.g. questions about "feminists" and "liberal media" are trolls, programming questions are rarely insincere).
* question structure is a big give away. Questions starting with "Why" were insincere 22% of the time, questions starting with "Where", "What" or "Which" are insincere less than 2% of occasions.
* there's a lot of text cleaning to do. Some ideas emerged, such as correcting "r" (e.g. "why r people who..."") to "are".


### [Step 1: Topic Modeling and Sentiment Analysis V1](notebooks/1_Topic_and_sentiment_V1.ipynb)


Article and Kernels to review:

[Improve your Score with some Text Preprocessing](https://www.kaggle.com/theoviel/improve-your-score-with-text-preprocessing-v2)
[example cleaning and keras model](https://github.com/KevinLiao159/Quora/blob/master/kernels/submission_v50.py)

[Topic Modeling with LSA, PLSA, LDA & lda2Vec](https://medium.com/nanonets/topic-modeling-with-lsa-psla-lda-and-lda2vec-555ff65b0b05)

[Text Classification: The First Step Toward NLP Mastery](https://medium.com/data-from-the-trenches/text-classification-the-first-step-toward-nlp-mastery-f5f95d525d73)
[Basic baseline models](https://www.kaggle.com/tunguz/just-some-simple-eda)
[TFIDF-NaiveBayes-LogReg Baseline](https://www.kaggle.com/ryanzhang/tfidf-naivebayes-logreg-baseline)

[Embed, encode, attend, predict: The new deep learning formula for state-of-the-art NLP models](https://explosion.ai/blog/deep-learning-formula-nlp)
[Pytorch](https://www.kaggle.com/artgor/text-modelling-in-pytorch)
[RNN](https://www.kaggle.com/kratisaxena/eda-classification-for-reviews-using-rnn)
[LSTM-CNN](https://www.kaggle.com/artgor/eda-and-lstm-cnn)
[LSTM + Attention Baseline](https://www.kaggle.com/suicaokhoailang/lstm-attention-baseline-0-672-lb)

[Transfer Learning!](https://www.kaggle.com/mschumacher/adding-an-auxiliary-task)

Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.testrun.org


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
