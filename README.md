# Best Quality Bean Juice
Collaborators: Kayli Aguilera, Annie Donnelly, Allyson McInnis, Liberty Heise

![coffee_3](https://user-images.githubusercontent.com/109040678/225430477-44e1c44a-f47f-4adc-ad08-dcf2c8323bc7.jpeg)

## Overview

Ever wonder what makes that cup of coffee taste so good?  Coffee must be planted, grown, picked, washed, dried and roasted, all before it gets to your coffee grinder, filtered and then brewed for your perfect cup.  But how does a coffee buyer choose from all the different regions, variations, altitudes and other variables?  We wanted to find out!

## Extract + Transform

Data was drawn from the Coffee Quality database to create the original CSV used in this project.  The CSV was then loaded into a Google drive to be used simultaniously by the team.  However, once we began working through our code for cleaning and sorting the data we realized the Google drive would not provide the correct access and switched it to a Visual Studio Code in which the original CSV files had to be downloaded from our shared GitHub repository. 

The data was extracted after being cleaned for nulls and also a quick hand-cleaning of data from the elevation column in which many entries were in the form of feet, symbols and other objects which would not have read into the dataframes properly, columns that were deemed unnecessary were removed from the set.  

## Machine Learning

<img width="630" alt="Screenshot 2023-03-16 at 7 26 13 PM" src="https://user-images.githubusercontent.com/109040678/226502324-31bffd9e-9914-40bc-8efb-06e30a5792d2.png">

<img width="630" alt="Screenshot 2023-03-16 at 8 33 08 PM" src="https://user-images.githubusercontent.com/109040678/226502350-e9f52a33-b8d4-46eb-a4e8-20e28a6b43ef.png">

## Tableau

The CSVs were loaded into Tableau and then utilized to observe and demonstrate differences and similarities between flavor profiles, countries of origin and other tabulations.  Ultimately, the data told a story in which linear regression was most helpful.  

We looked at coffee data from around the globe.
<img width="891" alt="Screenshot 2023-03-20 at 8 00 33 PM" src="https://user-images.githubusercontent.com/109040678/226501388-53f66d84-474a-4b9b-af0e-827b3f353058.png">

Then, we looked at the difference between flavor profiles and the total cup points by country of origin.  At this point in the visualization, it was apparent that the data was linear and correlated.  However, we continued to work on finding meaning through our neural network machine learning.  
<img width="1024" alt="Screenshot 2023-03-20 at 8 00 56 PM" src="https://user-images.githubusercontent.com/109040678/226501426-4cd6075f-778d-4549-aeb7-cf6a6859302c.png">

Looking at comparative data from number of products being cupped and cupping numbers, it was apparent that Central and South America had the highest quantity of coffee with Mexico being at the top.  However, cup averages are almost all the same, in the 80's.
<img width="875" alt="Screenshot 2023-03-20 at 8 01 26 PM" src="https://user-images.githubusercontent.com/109040678/226501952-af718aca-ef87-411b-8702-a0522c2de5c3.png">

<img width="875" alt="Screenshot 2023-03-20 at 8 01 11 PM" src="https://user-images.githubusercontent.com/109040678/226501605-264b3f26-3850-469c-83db-33f3b20496e3.png">

Finally, the flavor profiles were transformed into a single calculated field to compare with total cup points for all countries of origin.  What we found were that these profiles were identical to the total cup points (minus ~20k due to the subtraction of non-useful columns).

<img width="648" alt="Screenshot 2023-03-20 at 8 01 50 PM" src="https://user-images.githubusercontent.com/109040678/226501930-dd34ddc7-5e43-4b73-acfe-ab05fb5b6e40.png">

The tools that we utilized were the following:
Python, Pandas, and Google Colab were used to complete the ETL process and Machine Learning
We used Scikit-Learn for our prediction models in Machine Learning
We utilized SQL to load our data into Tableau.
We then used Tableau for our table visualization
![analysys](https://user-images.githubusercontent.com/106696262/227063919-9a676016-d435-4e7b-9557-a39acbd26e9d.jpg)




