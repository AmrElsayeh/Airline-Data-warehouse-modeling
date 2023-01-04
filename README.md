# Airline-Data-warehouse-modeling
Analyze a big airline company's present business operations and develop the business by identifying new prospects by evaluating aircraft operations, the reservation process, and customer service interactions.

## The Grain:
1- F_Flight_Instance
The gain for this fact table is every flight instance of a single passenger.
2- F_Frequent_Flyer_Miles
The grain for this fact is every transaction or ride the frequent flyer made, either he redeems a reward or make more miles so his score increases.
3- F_Frequent_Flyer_Hotel
The grain for this fact is per booking in hotel, when a frequent flyer book night in a certain hotel for the number of nights during his transit.
4-F_Customer_Request
The grain is per customer request for every passenger.
5- F_Customer_Promotion
the grain for this fact is per redeem promotion for the frequent flyer.

## Dimensions:
• D_Airport
• D_Flight
• D_Aircraft
• D_Pilot
• D_Payment_Channel
• D_Date
• D_CCI_Stag
• D_Passenger
• D_Frequent_Flyer
• D_Redeem_Type
• D_Hotel
• D_Promotion
• D_CC_Interaction
• D_CCI_Severity

## Facts:
• F_Flight_Instance
• F_Frequent_Flyer_Miles
• F_Frequent_Flyer_Hotel
• F_Customer_Requests
• F_Customer_Promotion

## Assumptions:
A. Assumed that every passenger has a passenger key and frequent flyer id in case he has a frequent flyer id, or null if he doesn’t in the flight instance
B. Assumed that marketing team manually or automatically with a certain code and bash script that every month check the miles traveled for every passenger and decide if his status is upgraded or degraded, also give him his score if he is a frequent flyer
C. Assumed if the passenger exceeds 5000 miles, he will gain the blue card and get a frequent flyer id, from 5000-30000 he will be silver, reaches 30000 with last 2 years is gold, reaches 300000 miles with the last 2 years is elite, reaches 600000 with the last 3 years is Platinum
D. Assumed that score is calculated depends on the frequent flyer class if he is blue 1mile=1score.
if he is silver 1 mile = 2 score.
if he is gold 1 mile = 5 score.
if he is elite 1 mile = 10 score.
if he is platinum 1 mile = 20 score.
E. Assumed that with the score you can redeem an upgrade of the flight class from economic to class A for example.
Also, can redeem many rewards of shops related to the agency like clothes, devices etc. with certain score point.
Also, can redeem the score to book some days in certain hotels in the transit period.
F. Assumed that company has a contract with many hotels near the airport that transit occurs for the frequent flyers only, and its price is added to the ticket with a very small fare, also can be redeemed with frequent flyer score system, and we record the price of night that we added on ticket, class of hotel in case that frequent flyer want to increase the hotel class.
G. Assume that reservation process can be done by several channels like application, offline from window, website or by calling.
