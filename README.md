# Data_Analysis_Customer_Data
The main aim of the project is to Develop input features. I have used two datasets the Visitor log data and User Data. The datasets can be downloaded from the link https://datahack.analyticsvidhya.com/contest/job-a-thon-june-2021/download/train-file
Visitor Log Data – It is a browsing log data of all the visitors and the users. This table contains the following information:



![Screenshot](Table1.png)

Now based on the above two tables, you need to create an input feature set for the Marketing Model.

![Table2](Table2.png)

Merging both the above datasets two create a userdatabase on the UserID column, 
UserID                0
Signup Date           0
User Segment          0
Reg_date              0
Reg_time              0
webClientID           0
VisitDateTime    123554
ProductID         51963
Activity          87757
Browser               0
OS                    0
City             236124
Country           42827
Visit_Date       123554
Visit_Time       123554

After merging I found that VisitDate has lots of missing values, The missing values of VisitDateTime columns cannot be filled so we are dropping the rows which have missing VisitDateTime entries


