# Data_Analysis_Customer_Data
The main aim of the project is to Develop input features. I have used two datasets the Visitor log data and User Data. The datasets can be downloaded from the link https://datahack.analyticsvidhya.com/contest/job-a-thon-june-2021/download/train-file
Visitor Log Data – It is a browsing log data of all the visitors and the users. This table contains the following information:



![Screenshot](Table1.png)

Now based on the above two tables, you need to create an input feature set for the Marketing Model.

![Table2](Table2.png)

Merging both the above datasets on the UserID column, to create a userdatabase  

![Table3](Table3.png)

After merging I found that VisitDate has lots of missing values, The missing values of VisitDateTime columns cannot be filled so we are dropping the rows which have missing VisitDateTime entries

Now for missing values in the Country, I found some of the entries has the city name attached along with the country name in the Country columns,We need to separate the city from the country name. For this I have created a list of countries available in the world using pycountry module. After that I have created a function which will iterate throuugh every rows and match the name of the Country of the user with the Country list created ,If 


