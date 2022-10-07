## Project and Author info
Project:  Reddit API and Binary Classification<br />
Author: Dennis Chan Zhen Ye


## Contents
- [01_data_collection](code/01_data_collection.ipynb)
- [02_data_cleaning_&_EDA](code/02_data_cleaning_&_EDA].ipynb)
- [03_preprocessing_&_modelling](code/03_preprocessing_&_modelling.ipynb)
- [Datasets](datasets)
- [Presentation](presentation/projet_presentation.pdf)


## Data Dictionary
Since the Data was scraped from the Reddit API, all the scraped data and features engineered along the way that are useful are presented in the table below.

| Feature    | Data Type | Data Description                                        |
|------------|-----------|---------------------------------------------------------|
| selftext   | string    | text of the subreddit post                              |
| title      | string    | title of the subreddit post                             |
| subreddit  | int       | subreddit that the post comes from                      |
| all_text   | string    | combination of the text and title of the subreddit post |
| word_count | int       | total number of words in all_text column                |




## Problem Statement
**Context / Motivation** <br />
The New Jersey's Supreme Court victory in May 2018 which allows any state that wishes can legalize sports betting has led to a boom in the sports betting business as casinos and sports betting sites to capitalise on the sector. Sports betting is now legal in states such as Pennsylvania and New York and other states are considering the to legalise it in the near future due to the substantial amount of tax revenue it could generate (Rodenberg, 2020).


As part of the effort to penetrate the sports betting market, our marketing team has been tasked by a large landbased casino with coming up with an effective marketing strategy to bring in new gamblers within the states where sports betting is legal. The marketing team has came up with a way to maximise impressions and lower future attrition rate by using targetted advertising, where sports fans who searches for keywords such as 'basketball' on google would be targeted with NBA related sportsbetting ads, while 'soccer' would prompt EPL (english premier league) ads. A similar strategy is deployed on other social media websites such as Facebook, where Facebook users who like the page of various NBA related keywords such as 'Lebron James' would be given an NBA ad, and the same goes for EPL related keywords.




**Primary & secondary audience** <br />
priimary audience are the marketing executives or market strategy teams in the sports betting companies as they need to understand which are the keywords that would improve the results of the marketing campaigns.

secondary audience are the clients that hired the marketing executives. Though they do not have to understand the inner workings of how the data works. It would be insightful for them to understand how certain important keywords impact their overall business.



**Business problem statement** <br />
Key words are important so as to lower the customer attrition rate which is a metric used to measure employees or customers lost over a period of time who are not replaced. The more accurate the key words and posts are classified , the more likely that the keywords impressions are made to the right audience and thus lowering the customer attrition rate. In other words, as soccer fans are more likely to bet on soccer matches, while basketball fans are more likely to bet on basketball matches, showing a soccer fan a basketball betting ad might cause not only less initial interest in the subject of sports gambling as he clicks into the ad, but he or she is also unlikely to be retained as a long term customer at the sport betting site. Thus, it is imperative that the right potential customers are shown the right ads.



**Data Science problem statement** <br />
The team is tasked with collecting posts from two subreddits: r/nba and r/PremierLeague, and then using NLP to train a classifier on which subreddit a given post came from. This problem is a binary classification problem that could be tackled with different combinations of vectorizer such as countVectorizer and tfidfvectorizer as well as different classifier models such as Logistic Regression and Naive Bayes Classifier. The dataset will be scraped from the Reddit API for the 2 subreddits and then splitted into the train and test datasets. The train dataset will be fitted into the classifier models and the best model (i.e the model with the best AUC ROC score) will be used to predict the test dataset. Success of the project will then be evaluated based on well the classifier model performs for the test dataset.






## Executive Summary
**Intention** <br />
This report provides a binary classification analysis of the two subreddits: r/nba and r/PremierLeague. Methods of analysis used in this report include the use of NLP, sentiment analysis, Vectorising text data (CountVectorizer, Tfidfvectorizer) and fitting into classification models (Logistic Regression, Niave Bayes Classifer). The data are evaluated based on model score, F-score, and AUC ROC score. In this case, it appear that the AUC ROC score is the most appropriate as the dataset is not imbalanced.


**Process** <br />

1. [Data Collection](code/01_data_collection.ipynb)
 - Scrapping Data from NBA subreddit
 - Scrapping Data from EPL subreddit


2. [Exploratory_Data Analysis (EDA)](code/02_data_cleaning_&_eda.ipynb)
 - Data Cleaning for NBA and EPL data
 - EDA
 - Feature Engineering
 - Binarizing Subjects
 - Visualizing Data: Box Plot Analysis
 - Sentiment Analysis
 - Identification of Common Terms in Text Data


3. [Preprocessing_&_Model Selection](code/03_preprocessing_&_modelling.ipynb)
 - Baseline Accuracy
 - Model Prep
 - Logistic Regression Model
     - CountVectorizer
     - TFIDVectorizer
 - Naive Bayes Model
     - CountVectorizer
     - TFIDVectorizer
 - Final Model Evaluation
 - Conclusion and Recommendations


**Key Findings** <br />
- Results of the data analysed show that the naive bayes / count vec model is produces the highest ROC AUC score of 0.995 and is thus should be chosen as the final model used to classify posts
- The report also finds that the r/PremierLeague subreddit seem to have more positive sentiments than NBA fans
- The negative sentiments on both subreddits seem to be minimal.
- Another finding is that the most commons words are of atheletes or players in the subreddit




## Recommendations and Conclusion


**Conclusion and Recommendations**
- Does the student provide appropriate context to connect individual steps back to the overall project?
- Is it clear how the final recommendations were reached?
- Are the conclusions/recommendations clearly stated?
- Does the conclusion answer the original problem statement?
- Does the student address how findings of this research can be applied for the benefit of stakeholders?
- Are future steps to move the project forward identified?

As stated above, the model is useful for predicting whether a reddit post belongs to the r/nba or r/PremierLeague subreddit, and thus it is a useful gauge to understand the keywords, interests and groups and such sports fans belong to. However, a major area of weakness is that it likely unable to classify vague words that are shared between both sports. Words such as "season" could be applied to either sports and thus the model is unlikely to be able to classify it effectively. As such, the predictions generated by the model is most effective when it is specialised, with words such as the names of nba or epl atheletes in the post (either title and selftext).

Besides the usefulness of the model as an input for understanding the keywords that could then market sportsbetting to the relevant audience, other business applications could also be derived from the results such as knowing what to write in the ads targeted at each group. EPL fans seem to have more positive sentiments than NBA fans, thus the advertising messages directed towards them could also be phrased in a more positive manner. In general, negatively worded advertising messages should be avoid since the negative sentiments on both subreddits seem to be minimal. Given the pervalence of atheletes or players in the subreddit, perhaps hiring such players as the spokesperson would also be an effective way to connect with the fans. Another insight is that advertising messages should be kept to between 52 to 119 words for NBA ads, and 32 to 96 words for EPL ads as this is inline with the interquartile range of the word count.


## Citation
Rodenberg, R. (2020, November 03). United States of sports betting: An updated map of where every state stands. Retrieved January 14, 2021, from https://www.espn.com/chalk/story/_/id/19740480/the-united-states-sports-betting-where-all-50-states-stand-legalization
