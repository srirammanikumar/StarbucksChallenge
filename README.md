# Starbucks Challenge

The main goal of this project is to identify if more offers should be sent to a customer based on the customer's previous purchase trends


## Data sets

All data used in this project are mock data. In the real world the data would contain multiple products, and each product would have multiple offers.
the model is trained on 3 major data sets -

- Portfolio - this contains the list of offers, and related data. 
- Profile - this contains the list of registered users with Starbucks, and their data like age, salary, gendex etc.
- Transcript - the list of all transactions, like purchase transactions, offers viewed, offers sent 


## Cleansing data

- Group the transactions on person
- one record for each type of offer
- Get the count of each type of offer - number received, number viewed, number completed
- merge data from Profile to get the person details
- merge data from Portfolio to get offer dtails


## Algorithm to send or not send more offers

- set output = 0 or 1.
- 1 means to keep sending offers
- 0 is to stop sending offers
- if a person has viewed and used an offer, or if he has not viewed and not used.. V - C = 0 keep sending more offers
- if a person has viewed offers but not used all of them. V-C > 0 & C > 0 .. keep sending offers
- if a person has seen offers but never used them. V-C > 0 & C = 0.. Do not send more offers
- if a person has used more offers than the offers viewd. V-C < 0 .. Do not send more offers


## Model used

A simple Adaboost Classifier gave an accuracy of 99%
