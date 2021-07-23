# Data_Analysis_Customer_Data
The main aim of the project is to Develop input features. I have used two datasets the Visitor log data and User Data. The datasets can be downloaded from the link https://datahack.analyticsvidhya.com/contest/job-a-thon-june-2021/download/train-file
Visitor Log Data – It is a browsing log data of all the visitors and the users. This table contains the following information:



![Screenshot](Table1.png)

Now based on the above two tables, you need to create an input feature set for the Marketing Model.

![Table2](Table2.png)

Merging both the above datasets two create a userdatabase on the UserID column, 
![Table3](Table3.png)

After merging I found that VisitDate has lots of missing values, The missing values of VisitDateTime columns cannot be filled so we are dropping the rows which have missing VisitDateTime entries


