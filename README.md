# Twitter Sentiment Analysis using NLP

![image](https://github.com/SeamusW/NLP-Tweet-Emotions/assets/32468677/da97edd3-1168-4a42-bf1b-8abc0441740a)

# Twitter Sentiment Analysis using NLP
*Seamus Walsh and Daniel Gieseke  |  July, 2023*

## Overview
Life expectancies vary over countries globally. With this project we are aiming to create a model that will predict a country's life expectancy at birth based on a variety of factors. Not only is this project focused on building a strong predictive model, this project further aims to look into which country features prove to be the most important when considering life expectancy at birth. This data was sourced from The World Bank and the United Nations via Kaggle.

## Project and Data Links
<a href="https://github.com/DGieseke/Global-Life-Expectancy-Predictions-Based-on-International-Metrics/blob/main/Data%20Modeling%2C%20Testing%2C%20and%20Predictions%20-%20International%20Life%20Expectancy.ipynb">Data Modeling, Testing, and Predictions</a>

<a href="https://github.com/DGieseke/Global-Life-Expectancy-Predictions-Based-on-International-Metrics/blob/main/EDA%20and%20Data%20Preparation%20-%20International%20Life%20Expectancy.ipynb">EDA and Data Preparation</a>

<a href="https://github.com/DGieseke/Global-Life-Expectancy-Predictions-Based-on-International-Metrics/blob/main/Predicting%20Global%20Life%20Expectancy.pdf">Project Slide Deck</a>

<a href="https://www.kaggle.com/datasets/truecue/worldsustainabilitydataset?select=WorldSustainabilityDataset.csv">Data Source: The World Bank and United Nations' Sustainability Data via Kaggle</a>


## Business and Data Understanding
For this project we play the role of world health advisors to nation leaders. It should be a foundational goal of all leaders to provide a sufficient quality of life for their citizens. Life expectancy has long been a crucial indicator of the overall health and well-being of the population, and can serve as a measure of a country’s quality of life. There are many factors that contribute to life expectancy:
<ul>
  <li>Wealth</li>
<li>Education</li>
<li>Energy Production and Consumption</li>
<li>Political Governance</li>  
</ul>
Using data provided by The World Bank and the United Nations, we've provided several data-drive strategies to increase life expectancy across the globe.

## Data Analysis
For our analyses we sought to predict and classify life expectancies at either above or below 70 years, which is the mean age of life expectancies across our data. We then looked at the biggest contributers to a higher life expectancy to advise countries on where they should provide interventions in order to improve their outcomes.

## Exploratory Analysis
After doing all of the necessary data cleaning, we started to explore features. Below, you can see our features of interest by correlation to Life Expectancy at Birth. Note, this visualization includes the correlation between columns with discrete data as our categorical columns may not provide the most insight here. From the below visualization, we see that "Access to Electricity", "GDP per Capita" and "Percent of Urban Population" are the features most correlated with Life Expectancy at Birth.

Below are visualizations that we believe shed light on these points.  For additional narratives and context, please see our jupyter notebook file.

**Relationship Between Life Expectancy at Birth and Access to Electricity**
![image](https://github.com/DGieseke/Global-Life-Expectancy-Predictions-Based-on-International-Metrics/assets/32468677/5594c4a8-9e4d-44d4-b552-e2bcefb41358)

**Relationship Between Life Expectancy at Birth and the Percent of a Population in Urban Areas**
![image](https://github.com/DGieseke/Global-Life-Expectancy-Predictions-Based-on-International-Metrics/assets/32468677/a3c86680-bb03-4d01-bb35-f9aa11cee7c2)


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
