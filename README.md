# Call_Center_Trends_Dashboard
able of Contents :
Problem Statement
Datasource
Data Preparation
Data Modelling
Data Analysis (DAX)
Data Visualization Dashboard
Insights
Problem Statement :
In this project Create a dashboard in Power BI for the call center manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset.

Possible KPIs include (but not limited to):

Overall customer satisfaction
Overall calls answered/abandoned
Calls by time
Average speed of answer
Agent’s performance quadrant -> average handle time (talk duration) vs calls answered
Datasource :
Dataset used for this task was presented by Pwc and call centre trends dataset:

Dataset: Call Centre Trends

Data Preparation:
Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Call Centre Trends dataset is give table named:

Call Center trends dataset which has 10 columns and 5000 rows of observation
Data Cleaning for the dataset was done in the power query editor as follows:

Removed Unnecessary columns
Removed Unnecessary rows
Each of the columns in the table were validated to have the correct data type
Data Modeling:
And then dataset was cleaned and transformed, it was ready to the data modeled.

The measure table and call centre trends tables as show below:
-Screenshot (37)

Data Analysis (DAX):
Measures used in all visualization are:

Average of seed of answerd = AVERAGE('call centre trends'[Speed of answer in seconds])

Average of statisfaction = AVERAGE('call centre trends'[Satisfaction rating])

Count satisfation rating = COUNT('call centre trends'[Satisfaction rating])

Overall Customer Satisfation = DIVIDE([Possitive satisfation rating],[Count satisfation rating],0)

Possitive satisfation rating = CALCULATE(COUNT('call centre trends'[Satisfaction rating]),FILTER('call centre trends','call centre trends'[Satisfaction rating] IN {4,5}))

resolved calls = COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "Yes"), 'call centre trends'[Resolved])

Unresolved calls = COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "No"), 'call centre trends'[Resolved])

total calls = CALCULATE('Table'[total calls answered] + 'Table'[total calls unanswred])

total calls answered = COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "Yes"),'call centre trends'[Answered (Y/N)])

total calls unanswred =COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "No"), 'call centre trends'[Answered (Y/N)])

Data Visualization (Dashboard) :
Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Dashboard: View Dashboard

Shows visualizations from Call Center Trends :
