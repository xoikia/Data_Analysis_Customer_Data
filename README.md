# Data_Analysis_Customer_Data
The main aim of the project is to Develop input features. I have used two datasets the Visitor log data and User Data. The datasets can be downloaded from the link https://datahack.analyticsvidhya.com/contest/job-a-thon-june-2021/download/train-file
Visitor Log Data – It is a browsing log data of all the visitors and the users. This table contains the following information:



![Screenshot](Table1.png)

Now based on the above two tables, you need to create an input feature set for the Marketing Model.

![Table2](Table2.png)

Merging both the above datasets on the UserID column, to create a userdatabase  

![Table3](Table3.png)

After merging I found that VisitDate has lots of missing values, The missing values of VisitDateTime columns cannot be filled so we are dropping the rows which have missing VisitDateTime entries

## Filling missing values in Country columns
Now for missing values in the Country, I found some of the entries has the city name attached along with the country name in the Country columns,We need to separate the city from the country name. For this I have created a list of countries available in the world using pycountry module. After that I have created a function which will iterate throuugh every rows in the dataframe and with the help of regularexpression's findall method it will find the name is availble in our list created and if it finds  the name of the Country of the user in the Country list created, It will replace the country name those have city name attached with the actual country name. 

To fill the missing values in the country , I have used three different steps:
Some of the users have accesed the site from more than one country. So in order to fill the missing values of the Country.

#### There are three different approach:

1.For users which have ordered only from one single country ,we just need to map its userid to a dictionary which contain userid as key and its country name from which it has given maximum order as  value, It will give its country name.It won't matter if the city column is missing or not for users who have ordered from a single country.


2.For users which have ordered from more than 1 country and the City value is also missing for that particular entry ,We will fill the country column with that country from where he has ordered maximum number of times and later filling the city column by the city from which he has ordered maximum number of times of that country.

3.But the above process will not work for users who have ordered from more than 1 country and whose city value is not missing .Suppose a user has ordered from India and USA. If for a particular entry if the city name is given as NewYork and we found that the user has ordered maximum number of times from India. We will fill the country name with wrong value.It should be USA. For such cases we have to map both the userid and  city to get the country name.

After completing the above three steps if any rows has Country data missing we will drop those entries.


## Filling missing values of City
I have created a nested dictionary from the above dataframe where UserID is the main key and City name as the key of nested dictionary and the name of the Country as the value
The format of the dictionary will be  
######## {'UserID':{'Country':'City'}}


