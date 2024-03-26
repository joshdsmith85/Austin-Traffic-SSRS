# Austin Traffic

1st- load data into SQL
Create Database for AustinTraffic.
Loaded a csv file from Austintexas.gov to get the traffic reports into a new table under the AustinTraffic database.


2nd - Connecting the Data to the reporting.
Created the connection to the Datasource.
Create the dataset needed using the following SQL code
SELECT
       [Traffic Report ID]
      ,CAST(LEFT([Published Date],10) AS DATE) AS DATE
	  ,LEFT(CAST((CAST(LEFT([Published Date],22) AS datetime)) AS TIME), 8) AS TIME
      ,[Issue Reported]
      ,[Location]
      ,CONCAT([Latitude], ',', [Longitude]) AS Coordinates
      ,[Address]
      ,[Status]
      ,[Status Date]
      ,[Agency]
  FROM [AustinTraffic].[dbo].[Real_Time_Traffic_Incident_Reports]

  3rd creating reports
  Created the first report to show the daily reports and the count for the total of daily reports.
  Created a bar chart to show the highest count of incidents reported.

  With these reports we are able to see the daily report and see that the Traffic hazards and crash urgents are the most common incidents.
