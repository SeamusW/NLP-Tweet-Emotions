# Twitter Sentiment Analysis using NLP

![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/da97edd3-1168-4a42-bf1b-8abc0441740a)

# Twitter Sentiment Analysis of Apple and Google Products using Natural Language Processing
*Seamus Walsh and Daniel Gieseke  |  July 14, 2023*

## Overview
Twitter among other social media platforms boasts an immense amount of consumer reviews, thoughts, critiques, and praises; with this project, we aim to build a Natural Language Processing (NLP) model that utilizes 'tweets' from Twitter to predict the general sentiment surrounding Apple and Google as well as their respective products. This data was sourced from Twitter via data.world and includes tweets along with respecitve, pre-determined emotion -- either "positive", "negative", "no emotion", or unknown. Our goal is to create a model that can read in one of these tweets and predict wheter the tweet is "positive", "negative", or "no emotion". 

## Project and Data Links
<a href="https://github.com/SeamusW/NLP-Tweet-Emotions/blob/main/Modeling%20and%20Final%20Analysis.ipynb">Modeling and Final Analysis</a>

<a href="https://github.com/SeamusW/NLP-Tweet-Emotions/blob/main/EDA%2C%20Processing%2C%20and%20Feature%20Engineering%20-%20Twitter%20Sentiment%20Analysis%20Project.ipynb">EDA and Data Preparation</a>
 
<a href="https://github.com/DGieseke/Global-Life-Expectancy-Predictions-Based-on-International-Metrics/blob/main/Predicting%20Global%20Life%20Expectancy.pdf">Project Slide Deck</a>

<a href="https://www.kaggle.com/datasets/truecue/worldsustainabilitydataset?select=WorldSustainabilityDataset.csv">Data Source: The World Bank and United Nations' Sustainability Data via Kaggle</a>


## Business and Data Understanding
It is a goal of all public facing organizations to keep a "pulse-check" on how their consumers feel about their product. One of the biggest places on the internet that consumers go to air their grievances and shout their praises, is Twitter. While it's impossible to gain much insight from one single person's tweet alone, having an understanding of thousands or even millions of tweets can be an enormous benefit. We've created a model that can filter MANY tweets at once, and provide accurate predictions on their sentiment that organizations can then use to advance their product.


## Data Analysis
For our analyses we sought to predict and classify tweets as either "positive", "negative", or "neutral". Our goals was to create a model that can read in a tweet and predict it's sentiment with high accuracy. Below, we've included some exploratory analysis, visualizations, and our final model.



## Exploratory Analysis
After doing all of the necessary data wrangling and cleaning, we took a look at the breakdown of emotion classifications in our data. 
![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/b811d60b-ffbe-440d-90a6-0d10bc9a13cd)
We can tell from the above visualization that our "target" feature is highly variable. We take this into account when preparing our model by using "SMOTE" to balance our target features.

Additionally, due to the low sample, and the small intrinsic value, we drop the "I can't tell" tweets from our data so we are only focusing on the "positive", "negative" and "no emotion" classifications.


## Breakdown of Products Tweeted About by Count
![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/8823cabd-2177-4e1a-83b2-5162eebb121e)


## Consumer Tweets by Product and Sentiment
![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/219cb95d-b734-410f-98ed-5c07f3d3b379)



## Exploring Vocabulary between Positive and Negative Tweets

### WordCloud of Vocabulary from Negative Tweets
![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/8df05da3-9bbb-4629-a065-2b28cba70a1a)



### WordCloud of Vocabulary from Positive Tweets
![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/c0ab03f3-d335-43ab-be49-3646bfcb92a4)



## Baseline Model
For our first model, we started with a Random Forest Classifier. We received a training accuracy score of .99 and a test accuracy of .85. For a first model, this looks pretty good!
![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/6cf47eb6-f41b-4086-bd2a-6d523ffad498)


## Logistic Regression Model
One model that specifically performed slightly better than others on accurately predicting negative tweets was the Logistic Regression Model. It received a training accuracy score of .93 and a test accuracy score of .85.
![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/20b59df9-82e9-45dc-99db-869ec3803d2e)


## Final Model
After testing several different models, the one with the best results was the XGBoost Classifier. It had a training accuracy score of .96 and a test accuracy score of .86. Looking at the difference in scores between this and our initial model, this one seems to be overfitting less, and should perform better on unseen data, which is why it was chosen as the final model. However, if you are more interested in exploring negative feedback about your product, we would recommend using the Logistic Regression Model instead.
![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/79c466b1-ed12-4d31-ad3b-3d97a566eb49)




## Recommendations
<li>Gauge implicit brand favorability using our model
<ul class="square">
  <li>Because these are implicit feelings, they have arguably more value than other industry measures on customer satisfaction</li></ul>
<li>Track sentiment trends
 <ul class="square">
   <li>By gathering this information over time, you can use to track trends and make interventions.</li></ul>ul>
<li>Hone in on consumer critiques in negative tweets
<ul class="square">
  <li> Based one the service recovery paradox, focusing on the negative critiques can turn detractors into promoters</li></ul>

## Next Steps
<li>Generate model based on expanded metrics
<li>Integrate data from other companies for cross-comparison
<li>Gather more data

## Repository Structure
  <b>daniel folder</b> This folder houses Daniel's working documents.

  <b>seamus folder</b> This folder houses Seamus's working documents.

  <b>data folder</b> This folder houses the .csv files we used to create these analyses.
  
  <b>Predicting Global Life Expectancy - Slide Deck</b> This file is a slide deck covering our analysis.

  <b>EDA and Data Preparation - International Life Expectancy</b> This file contains our data wrangling and exploratory analysis.

  <b>Data Modeling, Testing, and Predictions - International Life Expectancy</b> This file contains all of our models and analysis.
  
  
  <b>README.md</b> This is the file you are reading now that gives an overview of our project.
