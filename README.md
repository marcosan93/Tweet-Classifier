# Tweet Classification
**Collaborators:** Marco Santos & Harris Nathel

## Table of Contents:
* [Goal](#Goal)
* [Data Gathering](#Data-Gathering)
* [Data Cleaning](#Data-Cleaning)
* [Data Exploration](#Data-Exploration)
* [Classification Modeling](#Classification-Modeling)
* [Deep Learning with Keras](#Deep-Learning-with-Keras)
* [Potential Improvements](#Potential-Improvements)
* [Closing](#Closing)

## Goal
Given a specific subject and two different cities. Using NLP and classification models; can a tweet be classified as coming from the first or second city by regarding its language towards the specific subject?


## Data Gathering
- Used the module **Twint** to webscrape tweets from Twitter
- Specific tweets were scraped based on a **user-defined subject**
- Tweets were selected by **two user-defined cities**
- _Any subject and two cities_ can be inputted within the program to test the classifiers
- 10,000 tweets were grabbed from the two different cities totaling 20,000 tweets

For the sake of consistency, the focus for this specific iteration was on the subject of **Trump** within **Seattle** and **Jacksonville**.

## Data Cleaning
- Lowercased all words for every tweet
- URLs and special characters such as emojis and punctuations were removed
- *Lemmatization* with the **nltk** library was used for the remaining words

## Data Exploration

## Classification Modeling
* [Dummy Classifier - Baseline Model](#Dummy-Classifier)
* [Random Forest](#Random-Forest)
* [Naive Bayes](#Naive-Bayes)
* [Logistic Regression](#Logistic-Regression)
* [Support Vector Machine](#Support-Vector-Machine)

### Vectorizing
Both **CountVectorizer** and **tf_idfVectorizer** were used in order to compare the performance of the models with each. In the end, the performance for both were similar but tf_idfVectorizer had slightly better overall results. As a result, **tf_idfVectorizer** was chosen as the default Vectorizer.

### Dummy Classifier
#### Results:
Training Score - 50%

Testing Score - 49%

![](Images/dumconmat.png)

### Random Forest
#### Results:
Training Score - 96%

Testing Score - 60%

![](Images/rfconmat.png)

### Naive Bayes
#### Results:
Training Score - 79%

Testing Score - 62%

![](Images/nbconmat.png)

### Logistic Regression
#### Results:
Training Score - 82%

Testing Score - 61%

![](Images/lrconmat.png)

### Support Vector Machine
#### Results:
Training Score - 87%

Testing Score - 59%

![](Images/svmconmat.png)

## Deep Learning with Keras
A Sequential model was used with only 3 layers within the neural network.  After training for 300 epochs with a batch size of 256, the results were similar to the other classification models. No significant changes warranted the need for a neural network for the tweets.

## Potential Improvements
- More models could be applied such as XGBoost, KNN, etc. for more comparisons and potential improved results.
- Feature engineering such as _ngrams_ for possibly better results.
- More cleaning with other techniques or different modules such as *SpaCy*
- More experimentation with the neural network

## Closing
Due to the nature of the question, it is inherently difficult to classify whether a tweet comes from one location or not.  However, these classification models did perform better than randomly guessing (dummy classifier).  Most models performed at least 10% better than the Dummy Classifier and the best performing model was Naive Bayes. Even though these models performed this way for this dataset, a new subject and cities could significantly alter the overall results. 

