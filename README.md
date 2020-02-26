# Starbucks Capstone Challenge
 
## Project for Udacity Data Scientist Nanodegree 

## Table of Contents
Python Packeges used
Project Motivation
File Descriptions
Results
Licensing, Authors, and Acknowledgements

## This project is executed in a Jupyter Notebook with the help of below packages
Numpy
Pandas
Matplotlib
Seaborn
Calendar
Sklearn
math 
json
pickle 

## Project Motivation
It is the Starbuck's Capstone Challenge of the Data Scientist Nanodegree in Udacity. We get the dataset from the program that creates the data simulates how people make purchasing decisions and how those decisions are influenced by promotional offers. We want to make a recommendation engine that recommends Starbucks which offer should be sent to a particular customer.The goal of this project is to build a model that predicts how will the customer respond will to an offer.

## The data is contained in three files:
portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.) 
    * id (string) - Offer id
    * offer_type (string) - String that describes the offer type
        * bogo (Buy One Get One Free)  
        * discount
        * informational
    * difficulty (int) - Minimum amount a customer must spend to complete an offer
    * reward (int) - Reward given for completing an offer
    * duration (int) - Offer duration [days]  
    * channels (list of strings)


profile.json - demographic data for each customer 
    * age (int) - Customer age
    * became_member_on (int) - Date when customer created an app account
    * gender (str) - Customer gender (note some entries contain 'O' for other rather than M or F)  
    * id (str) - Customer id
    * income (float) - Customer's income  

transcript.json - records for transactions, offers received, offers viewed, and offers completed 
    * event (str) - Record description (i.e. transaction, offer received, offer viewed, etc.)
    * person (str) - Customer id
    * time (int) - Time in hours. The data begins at time t=0
    * value - (dict of strings) - Either an offer id or transaction amount depending on the record

## Results
•	The naive model accuracy was 0.471 and its F1-score was 0.640
•	Random forest model had the best accuracy (0.743) and F1-score (0.735) compared to gradient boosting, logistic regression
Rank	by Classifier Type	(Accuracy,	F1- score)
1	Random Forest	(0.743177,	0.734613)
2	Gradient Boosting	(0.735191,	0.72294)
3	Logistic Regression	(0.723203,	0.715932)
4	Naïve Predictor	(0.4688,	0.638344)

•	Using grid search we refined the Random forest hyperparameters and accuracy increase from 0.743 to 0.752 and F1 -score 0.735 to 0.742

The analysis suggests that a random forest model has the best training data accuracy and F1-score. The refined random forest model hyperparameters using a grid search suggests that the resulting random forest model has a training data accuracy of 0.752 and an F1-score of 0.742. The test data set accuracy of 0.733 and F1-score of 0.727 suggests that the random forest model we constructed did not overfit the data

The top five features based on their importance are- Reward, duration days, difficulty, income and whether a customer created an account on the Starbucks rewards mobile application in 2018.

Since the top three features are associated with a customer offer, it may be possible to improve the performance of a random forest model by creating features that describe an offer’s success rate as a function of offer difficulty, duration, and reward. These additional features should provide a random forest classifier the opportunity to construct a better decision boundary that separates successful and unsuccessful customer offers.

## Licensing, Authors, Acknowledgements
Must give credit to Stakbucks for the data
