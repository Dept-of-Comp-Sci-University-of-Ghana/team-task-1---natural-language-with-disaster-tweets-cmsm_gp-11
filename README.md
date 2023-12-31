[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/sRMOJrsa)


# Natural Language Processing with Disaster Tweets 

## Group 11 Report

<hr>

###  Group Members

Ebenezer Acquah - 10885076 <br>
Eugene Cobbah – 10866103

<hr>

## Dataset
The dataset includes three files:
train.csv: This file contains the training set data. It is used to train a machine learning model to predict whether a tweet is about a real disaster or not. The columns in this file include:

**id:** A unique identifier for each tweet. <br>
**text:** The text of the tweet. <br>
**location:** The location from where the tweet was sent (may be empty). <br>
**keyword:** A particular keyword from the tweet (may be empty). <br>
**target:** Indicates whether the tweet is about a real disaster (1) or not (0). <br>

**test.csv:** This file contains the test set data. It is used to evaluate the performance of the trained model on unseen data. The columns in this file are the same as in train.csv, except for the "target" column, which is not present since it needs to be predicted. <br>

**sample_submission.csv:** This file provides a sample submission format. It is used as a template to submit predictions for the test set. The columns in this file include:

**id:** A unique identifier for each tweet. <br>
**target:** The predicted target value (0 or 1) for whether the tweet is about a real disaster.

## Exploratory Data Analysis
The distribution of the target variable is plotted using a countplot, showing the distribution of disaster and non-disaster tweets.

![Distribution of Target Variables](/images/image.png "Distribution of Disaster Vs Non-disaster Tweet.")

<br>
A word cloud is also generated to visualize the most common words in disaster-related tweets.


![WordCloud](/images/image-1.png "Word Cloud - Disaster Tweets")

## Data Preprocessing
The text data is cleaned by removing URLs, usernames, hashtags, and non-alphanumeric characters. The text is converted to lowercase, stripped of leading and trailing spaces, and stopwords are removed.

## Feature Encoding
The text data is encoded into numerical vectors using the SentenceTransformer model.

## Model Training and Evaluation
Three models are trained and evaluated: Random Forest Classifier, LightGBM Classifier, and Support Vector Classifier. The models are trained using the encoded features and evaluated using validation accuracy.
The table below shows the summary of the results
| Model                 | Result |
|-----------------------|--------|
| SVC                   | 82.68% |
| LGBMClassifier        | 79.92% |
| RandomForestClassifer | 81.10% |


## Challenges
**Imbalanced Dataset:** The dataset had more non-disaster tweets than disaster tweets, making it challenging to train accurate models and evaluate their performance effectively.

**Text Cleaning and Preprocessing:** Cleaning and preprocessing the text data required careful handling of URLs, usernames, hashtags, and special characters. Ensuring proper cleaning while preserving important information was a task that required attention.

**Feature Encoding:** Converting the text data into numerical vectors using the SentenceTransformer model was computationally demanding and time-consuming, requiring efficient resource management.


## Conclusion
In this project, we analyzed a dataset of disaster tweets and trained models to predict if a tweet is about a real disaster. Through exploratory data analysis, preprocessing, and feature encoding, we achieved validation accuracies of 82.68% (SVC), 79.92% (LightGBM), and 81.10% (Random Forest). The SVC model performed the best, providing valuable insights for classifying disaster-related tweets.



