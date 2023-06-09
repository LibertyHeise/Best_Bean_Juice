# Best Quality Bean Juice
Collaborators: Kayli Aguilera, Annie Donnelly, Allyson McInnis, Liberty Heise

![coffee_3](https://user-images.githubusercontent.com/109040678/225430477-44e1c44a-f47f-4adc-ad08-dcf2c8323bc7.jpeg)

## Overview

Ever wonder what makes that cup of coffee taste so good?  Coffee must be planted, grown, picked, washed, dried and roasted, all before it gets to your coffee grinder, filtered and then brewed for your perfect cup.  But how does a coffee buyer choose from all the different regions, variations, altitudes and other variables?  We wanted to find out!

## Extract + Transform

### Extract
Data was drawn from the Coffee Quality database to create the original CSV used in this project.  The CSV was then loaded into a Google drive to be used simultaniously by the team.  However, once we began working through our code for cleaning and sorting the data we realized the Google drive would not provide the correct access and switched it to a Visual Studio Code in which the original CSV files had to be downloaded from our shared GitHub repository. 

Once we started to use VSCode, the first thing we did was download the database we found called “coffee_ratings.csv” which had the data qualities that we were searching for. We Extracted our data from the csv and imported it as a dataframe into jupyter notebook.

<img width="739" alt="Screenshot 2023-03-22 at 2 22 59 PM" src="https://user-images.githubusercontent.com/111312397/227069181-56ec9826-b453-448d-84a5-c1d5c12a3e63.png">


### Transform
After that we made multiple data frames so that we can see the accuracy based on flavor profile and demographics specifically. We dropped all the nulls from both data frames so our data would be more concise. We then focused on demographic df and changed the integer that was in place for the dates used in the “grading_date” column to a datetime format; the column “grading_date” was also changed to a datetime year. 


<img width="1001" alt="Screenshot 2023-03-22 at 2 28 23 PM" src="https://user-images.githubusercontent.com/111312397/227069385-36ced979-e20e-4d50-8fa0-fdc952c671ae.png">
<img width="1095" alt="Screenshot 2023-03-22 at 2 28 03 PM" src="https://user-images.githubusercontent.com/111312397/227069387-35e8673e-0897-4e55-bd31-2a4620fb78ad.png">

It was at this point when we were trying to narrow down some of our columns, did we see that there were some serious differences between the data in each column. The year sometimes had varying symbols in them that made it ununiform, as well as the elevation measurement types varied. The data was extracted after being cleaned for nulls and a quick hand-cleaning of data for anomalies in the columns was done. Other objects which would not have read into the dataframes properly along with columns that were deemed unnecessary were removed from the set. Finally we were able to upload the best version of the csv called “New_ETL.csv”.

<img width="181" alt="Screenshot 2023-03-22 at 2 17 30 PM" src="https://user-images.githubusercontent.com/111312397/227069416-4f32efde-6c34-48f0-8df6-4b1653fd8866.png">
<img width="140" alt="Screenshot 2023-03-22 at 2 17 14 PM" src="https://user-images.githubusercontent.com/111312397/227069419-cc69ec88-a75b-4915-845a-7e71ad3fb1e7.png">


In a last push to make our data more uniform, we made a “year_diff” column that subtracts the year that the coffee was graded (or tasted) from the year that coffee was actually harvested. We then made our new dataframes (demographic_df and flavor_profie_df) into new CSV’s so they would be ready to load into Postgresql.

<img width="931" alt="Screenshot 2023-03-22 at 2 57 27 PM" src="https://user-images.githubusercontent.com/111312397/227069471-043297f7-cdc0-4e71-a6f5-f93b38d5b785.png">


### Load
In our final steps, we uploaded our newly squeaky clean dataframes and concatinated them into one called coffee_df. We then pushed all of this to SQL and were able to see our new tables made within postgres.
 

## Machine Learning

For the machine learning portion of the project, the csvs that were created during the ETL process were used. To be able to apply them to machine learning the data need to be  converted into a usable form. The data points that were strings needed to be changed into integers. Once this was done the dataframes could be  implemented to multiple models or.

![image](https://user-images.githubusercontent.com/113384120/227066672-3a52c776-eb68-4699-88bd-ebb19ff81e37.png)

The first model that was used was to see if the data could be clustered. It was found that the data could be clustered. By utilizing the elbow curve we found that it could be clustered into two groups and possibly three. This backed the thinking of using two groups, flavor and demographics. To simplify the machine learning, both groups were used together in one dataframe for most of the models.

![image](https://user-images.githubusercontent.com/113384120/227066980-a3f9f1b0-db87-4753-91dc-1a6992d2b234.png)

To ensure that the dataset could be used for predictions a set of regressors were applied to it. We used regressors because our data is on a continuum rather than a binary scale. We found from the regressors that there appeared to be a good predictive data. As shown below.

![image](https://user-images.githubusercontent.com/113384120/227067079-a7d88759-92a2-4b61-8ce1-3def3e9359eb.png)

When the regressors showed that the coffee dataset could possibly be predictive it was applied to a deep neural network. The deep neural network was used to see what predictions, or if we could make predictions based upon the data that we had.  Many issues appeared, or more like one big issue, and that was our accuracy and  losses were way out of proportion to the regressors. To sum it up our accuracy never got over 0. Despite changing the number of nodes, the number of layers, the activation, and the compile model loss the accuracy remained 0 and our losses were exponential. Even when breaking down our main data set into the clusters of flavor and demographic accuracy and loss remain the same. What was found after taking a deeper look at the data was that the data points were not independent of each other. In other words, the column that was being used for prediction was dependent on the sum of flavor columns.

![image](https://user-images.githubusercontent.com/113384120/227067205-f4eb60ea-9faf-44f1-af57-2997d78cc7dc.png)
![image](https://user-images.githubusercontent.com/113384120/227067248-00cf49aa-735a-4615-bb1c-75d547363ccd.png)

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




