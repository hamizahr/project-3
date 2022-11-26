# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP


### Problem Statement

The app 'Seedly' is known to help users make smarter financial decisions with its expense tracking app, they have planned to further expand the community to include legal expertise/advice to help individuals with legal woes.

Their aim is to curate articles about legal matters and finance by using reddit to classify posts that are posted in subreddit personal finance and legal advice.

This is will give them a sense of what people are generally asking or posting about to create articles based on general population.


### Executive Summary

This project is to attempt at classifying posts from Reddit, and to identify if it was posted in r/personalfinance or r/legaladvice.


1. Data Scraping
Sources derived from Reddit Pushift API based scraping from 2 subreddits, both need to hit a minimum of 5000 posts and each post to contained 20 words and more. Posts with empty contents and emojis to be discared. Subreddits chosen was r/personalfinance and r/legaladvice

2. EDA
Appending title and selftext into 1 column and dropping duplicates and posts that have less than 20 words. After appending the columns, the subreddit column consists of NaN values this was then filled in. After cleaning up the following, the 2 dataframes then was merged to create a single dataframe for the next steps.

3. Pre-Processing & Modelling
Countvectorizer with stopwords hyperparameter was used to convert text data into a structured numeric df. TfidrVectorizer was also used to compared against the countvectorizer to see if there's a difference.

4. Evaluation
We evaluate the metrics of the chosen model which is the MultiNomial Naive Bayes that we have chosen by creating a matrix table to compare and make comparisons of the different metrics.


### Conclusion

To conclude the findings from the model, and to introduce ways to improve future models based on our analysis thus far.

Model | Train Score | Test Score
--- |--- | ---
Random Forest | 0.998 | 0.898
MultiNomial Naive Bayes | 0.934 | 0.919
Logistic Regression Model | 0.997 | 0.910


- The Multinomial Naive Bayes classifier performed well with a test accuracy score of 91.9%.

- Ways to improve future models:
1. Collection of more data points for modelling.
2. Tuning of hyperparameters will help with the accuracy of the train and test score.
3. Optimize other ML models to see which is best.
