# Twitter Sentiment Analysis using NLP

![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/da97edd3-1168-4a42-bf1b-8abc0441740a)

# Twitter Sentiment Analysis of Apple and Google Products using Natural Language Processing
*Seamus Walsh and Daniel Gieseke  |  July 14, 2023*

## Overview
Twitter among other social media platforms boasts an immense amount of consumer reviews, thoughts, critiques, and praises; with this project, we aim to build a Natural Language Processing (NLP) model that utilizes 'tweets' from Twitter to predict the general sentiment surrounding Apple and Google as well as their respective products. This data was sourced from Twitter via data.world and includes tweets along with respecitve, pre-determined emotion -- either "positive", "negative", "no emotion", or unknown. Our goal is to create a model that can read in one of these tweets and predict wheter the tweet is "positive", "negative", or "no emotion". 

## Project and Data Links
<a href="https://github.com/DGieseke/Global-Life-Expectancy-Predictions-Based-on-International-Metrics/blob/main/Data%20Modeling%2C%20Testing%2C%20and%20Predictions%20-%20International%20Life%20Expectancy.ipynb">Data Modeling, Testing, and Predictions</a>

<a href="https://[github.com/SeamusW/NLP-Tweet-Emotions/blob/main/EDA%2C%20Processing%2C%20and%20Feature%20Engineering%20-%20Twitter%20Sentiment%20Analysis%20Project.ipynb]">EDA and Data Preparation</a>

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


**Breakdown of Products Tweeted About by Count**
![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/8823cabd-2177-4e1a-83b2-5162eebb121e)


**Exploring Vocabulary between Positive and Negative Tweets**
WordCloud of Vocabulary from Negative Tweets
![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/8df05da3-9bbb-4629-a065-2b28cba70a1a)



WordCloud of Vocabulary from Positive Tweets
![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/c0ab03f3-d335-43ab-be49-3646bfcb92a4)



## Baseline Model
For our first model, we started with a simple Logistic Regression. We received a training accuracy score of .92 and a test accuracy of .91. We chose to look at the accuracy score because we had a fairly even balance in our target classifier. For a first model, this looks pretty good!

## Secondary Model
For our second model, we chose to use a Random Forest Classifier with default hyperparameters. We chose this model because it is simple to interpret, can run very fast, is less prone to over fitting, and can provide us information on feature importance.

For our second model, we received a training accuracy score of 1, and a test accuracy score of .98. A big improvement from our initial model.

## Final Model
For our final model, we wanted to piggy back on the success of our Random Forest classifier by trying to tune several hyperparameters using Grid Search. We specifically tuned the max depth, minimum samples to split, and minimum samples in a leaf parameters. 

After tuning, our final model received a training accuracy score of 1, and a test accuracy score of .98. Although our test score didn't increase, we are happy with our model now that we've confirmed the best levels of our hyperparameters.

Below you can see a confusion matrix showing the results of our final model.
![image](https://github.com/DGieseke/Global-Life-Expectancy-Predictions-Based-on-International-Metrics/assets/32468677/e08972dd-aa25-4970-830b-1203e73da3e4)

## Feature Importance and Recommendations
After exploring the feature importances of our final model we are giving 2 recommendations to nation leaders:
<ul>
<li>Invest in Electrical Infrastructure
<ul class="square">
  <li>Access to electricity proved to be the biggest weight in our predictive model. The more access people have to electricity, the greater the population's life expectancy</li></ul>
<li>Develop Urban Hubs
 <ul class="square">
   <li>The higher the percent of an urban population, the better life expectancy outcomes will be.</li>
   <li>On a macro level, it brings together diverse populations and has been shown to positively contribute to a countries financial growth. This can in itself increase access to daily necessities, and make simple a lot of things that are more strenuous, difficult and potentially dangerous in a rural environment</li></ul>
</ul>

## Next Steps
<li>Get more granular. What are the specific, best ROI interventions as they relate to our recommendations?
<li>Gather more data
<li>Work with developing countries directly

## Repository Structure
  <b>daniel folder</b> This folder houses Daniel's working documents.

  <b>seamus folder</b> This folder houses Seamus's working documents.

  <b>data folder</b> This folder houses the .csv files we used to create these analyses.
  
  <b>Predicting Global Life Expectancy - Slide Deck</b> This file is a slide deck covering our analysis.

  <b>EDA and Data Preparation - International Life Expectancy</b> This file contains our data wrangling and exploratory analysis.

  <b>Data Modeling, Testing, and Predictions - International Life Expectancy</b> This file contains all of our models and analysis.
  
  
  <b>README.md</b> This is the file you are reading now that gives an overview of our project.
