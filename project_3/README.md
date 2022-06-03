# Project 3: Web APIs & NLP

## Table of Contents
1. [Problem Statement](#1-Problem-Statement)  
2. [Executive Summary](#2-Executive-Summary)  
3. [Data Dictionary](#3-Data-Dictionary)  
4. [Model Results](#4-Model-Results)  
5. [Recommendations and Conclusion](#5-Recommendations-and-Conclusion)  
6. [Future Steps](#6-Future-Steps)  

![](https://github.com/andretch/Andre_Projects/blob/master/project_3/assets/car_motorcycle.jpg)  
[Source](https://images.prismic.io/rymax/YTYzNGY0ZmUtMmVmMi00NDVmLWIwMzEtYWIzZjcyYzEzMjM3_motorcycle-versus-car.jpg?auto=compress,format&rect=0,0,1280,853&w=1280&h=853)

## 1. Problem Statement
[Return to top](#Table-of-Contents)  

Our customer, a prominent auto magazine publisher, has engaged us to help with accurately classifying subreddits in an effort to identify if a post is from r/cars or r/motorcycle. They aim to use this data to position their editorials to better cater to the masses.  

In this project, we will use the [Pushshift API](https://github.com/pushshift/api) to perform web scraping of the two abovementioned subreddits from [reddit.com](reddit.com)


## 2. Executive Summary  
[Return to top](#Table-of-Contents)  

Following the Data Science workflow:
- Web scraping
- Data Cleaning  
- Pre-Processing & Feature Engineering  
- EDA  
![](https://github.com/andretch/Andre_Projects/blob/master/project_3/assets/car_wordcloud.jpg)  
![](https://github.com/andretch/Andre_Projects/blob/master/project_3/assets/bike_wordcloud.jpg)  
- Tokenizing  
    - CountVectorizer  
    - TF-IDF  
- Modeling  
    - Multinomial Naive Bayes Model  
    - Random Forest Model  

## 3. Data Dictionary  
[Return to top](#Table-of-Contents)  

|Feature|Type|Dataset|Description|  
|---|---|---|---|  
selftext | object | cars/motorcycle | text of post, 25 - 50% were labelled [Removed]  
title | object | cars/motorcycle | title of post  
upvote_ratio | float64 | cars/motorcycle | large portion (> 97%) 1.00   
subreddit | object | cars/motorcycle | which subreddit the data belongs to: cars/motorcycle  
author | object | cars/motorcycle | username  
is_self | bool | cars/motorcycle | True / False, False indicates the lack of selftext

## 4. Model Results  
[Return to top](#Table-of-Contents)  
TF-IDF \| RandomForestClassifier was the worst performing with an accuracy of 0.62.  
All other models had similar performance.  

|                                           | **RESULTS** |        |          |         |
|-------------------------------------------|-------------|--------|----------|---------|
| Tokenizer \| Model                        | precision   | recall | f1 score | support |
| CountVectorizer \| MultinomialNB          | 0.91        | 0.91   | 0.91     | 3938    |
| TF-IDF \| MultinomialNB                   | 0.91        | 0.91   | 0.91     | 3938    |
| CountVectorizer \| RandomForestClassifier | 0.91        | 0.91   | 0.91     | 3938    |
| TF-IDF \| RandomForestClassifier          | 0.71        | 0.62   | 0.57     | 3938    |


## 5. Recommendations and Conclusion  
[Return to top](#Table-of-Contents)  

With the problem statement in mind, which was to use NLP to classify posts from two subreddits r/cars and r/motorcycle using Pushshift's API, we have collected a total of 19,687 posts. After preprocessing, cleaning, EDA and modelling, we have come to the below conclusion.  

In general, the 3 of the 4 models yielded f1 score of 0.91. The TF-IDF vectorizer | Random Forests had the worst f1 score of 0.57. This is likely due to the large overlap of words between the two classes, of which TF-IDF reduces the importance of words that appear frequently.  

It seems like there is no clear best model to choose from. However, using our understanding of the problem and the nature of the models, this project is inclined to use either CountVectorizer | MultinomialNB or CountVectorizer | RandomForestClassifier as the selected model. CountVectorizer may be the better vectorizer for this problem in particular. Since the objective is to classify a post into a subreddit based on the post content, we actually want to assign more importance to the words that appear frequently in all the posts, such as "cars" and "motorcycle". This is exactly what count vectorizer does, as compared to TF-IDF vectorizer which reduces the importance of words that appear frequently.  

One of the biggest advantages of random forest is its versatility. It can be used for both regression and classification tasks, and it’s also easy to view the relative importance it assigns to the input features. Random forest is also a very handy algorithm because the default hyperparameters it uses often produce a good prediction result. Understanding the hyperparameters is pretty straightforward, and there's also not that many of them. One of the biggest problems in machine learning is overfitting, but most of the time this won’t happen thanks to the random forest classifier. If there are enough trees in the forest, the classifier won’t overfit the model.  
 
Hence, we recommend the CountVectorizer | MultinomialNB or CountVectorizer | RandomForestClassifier models for use with this problem satement.  

Since the selected tokenizer and model is able to achieve a f1 score of 91%, it significantly outdo the baseline score of 50.04%. The customer will be able to classify the posts from subreddits r/cars and r/motorcycle with a much lesser error of about 9%.  

With a "better than baseline" classification model, they will be able use this model to better position their editorials.  


## 6. Future Steps  
[Return to top](#Table-of-Contents)  
- Our model is limited to the corpus of texts obtained from scrapping cars and motorcycle reddit APIs. It would be better if the model can learn on its own, constantly update new text. This would allow the model to stay relevant longer.  
- Trying other models such as logistic regression, K-nearest-neighbors and support vector machines to compare performance
- Expanding the data set to include a larger vocabulary and time frame
- Perform sentiment analysis to further classify the posts into good/bad sentiments
