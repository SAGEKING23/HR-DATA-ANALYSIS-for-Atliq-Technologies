![DataANA](https://github.com/SAGEKING23/HR-DATA-ANALYSIS-for-Atliq-Technologies/assets/164085810/99d4540f-7d6e-4ce6-be92-1e2dfeae07da)
# Overview: HR Data Analytics for Atliq Technologies
This project aims to analyze the attendance data of employees at Atliq Technologies for the last three months. The goal is to provide insights to the HR Generalist regarding employee attendance patterns, retention strategies, and reasons behind sick leave percentages. Additionally, the analysis differentiates between Work From Home (WFH) and Work From Office (WFO) percentages.

## Table of Contents
1. Project Description
2. Data Source
3. Requirements
4. Technologies used
5. Methods
6. Results
7. Challenges and Milestones

## Data Sources
The attendance data was provided in an Excel file format. (Paste Link) Access as an editor can be granted upon request.

## Requirements
To accomplish the project objectives, the following steps were taken:

1. **Understanding the Problem:** Define the scope of the analysis, focusing on attendance patterns, retention strategies, and sick leave percentages.

2. **Data Gathering and Transformation:** Collect the attendance data from the provided Excel file and perform ETL operations to clean and transform the data into a suitable format for analysis.

3. **Creating Metrics using DAX:** Implement Data Analysis Expressions (DAX) to create key metrics, such as attendance percentages, sick leave percentages, WFH percentages, and more.

4. **Dashboarding with Power BI Desktop:** Utilize Power BI Desktop to visualize the data and create interactive dashboards. Develop visualizations to provide insights into attendance trends, sick leave reasons, WFH vs. WFO percentages, and other relevant metrics.

## Architecture Diagram

## Technology Used

The following technologies were used in this project:

* Excel
* MySQL
* PowerBI

## Methods
A step-by-step approach on how I created visuals in Power BI from Excel and MySQL data:

**Step 1: Data Preparation in Excel**
The data in the Excel file needed to be cleaned before using it in Power BI. The initial goal was to have the date as a column with all the counts per day for Present (P), Sick Leave (SL), Total Working Days (TWD), and Work From Home (WFH).

Example: how many employees registered as Present (P) on the 1st of June?

To achieve this, follow these steps:

 1. Highlight the entire table and copy it.

 2. Open a new worksheet in Excel, go to the first cell, right-click, and select "Paste Special" -> "Transpose."

 3. Add columns for P, SL, TWD, and WFH at the end.

 4. Use Excel functions to count P: =COUNTIF(range, "P"). This function counts the letter "P" for each day.

 5. Repeat step 4 for SL, WFH, and use =SUM(WFH + P) for TWD.


**Step 2: Data Transformation in MySQL**

When deleting unwanted columns (like the columns of individual employees) in Excel, it affected the formulas for P, SL, WFH, and TWD, causing errors. To solve this, I used MySQL:

1. Create a schema for HR attendance in MySQL.
2. Upload the modified data with the relevant columns to the MySQL table.
3. Execute the following SQL code to retrieve the data:

`SELECT date, P, SL, TWD, WFH
FROM attendance.attendance_tb;`

Note: 'attendance' is the schema name, and 'attendance_tb' is the table name.

I repeated this process for each month separately and saved the resulting tables.

**Step 3: Data Loading and Transformation in Power BI**

1. Upload the saved tables from MySQL into Power BI.
2. Before loading the data, further transform it in the Power Query Editor:
  + Ensure each column corresponds to the relevant data type.
  + Create or add a column for SL% using the DAX measure: SL% = [SL counts] / [Total working days].
  + Repeat the same for P% and WFH%.
3. Perform these steps for all three months.
4. Load the three datasets into Power BI.

**Step 4: Creating Visuals in Power BI**

1. Create visuals by dragging and dropping the relevant fields from the loaded datasets.
2. Use the Power Query Editor to combine data from all three months to create visuals for the overall period.
3. To create a bar chart with a line graph for each employee:
  + Use the Power Query Editor on the original (untransposed) Excel data.
  + Drop all columns except Employees, P, SL, PL, WFH, and TWD.
  + This data table will provide the total counts of P, SL, PL, WFH, and TWD for each employee per month.
By following these steps, you can transform the data from Excel and MySQL into visuals in Power BI.

## Results
Here is the preview of the dashboard.

![Presence Report](https://github.com/SAGEKING23/HR-DATA-ANALYSIS-for-Atliq-Technologies/assets/164085810/4ff4eab9-f4e5-46b0-952d-3b7d845a0c36)


Click the link below to download the dashboard and access in PowerBI. You must copy the link or click to open on your browser. https://drive.google.com/file/d/109kLmzmA2in_r0dpSY_NlQ-khKKnL_uI/view?usp=drive_link

You might need to install PowerBI desktop on your device first in order to access the file. You can follow this link to download PowerBI - https://powerbi.microsoft.com/en-us/downloads/


## Challenges and milestone

Completing the PowerBI dashboard wasn't as challenging as dealing with the data from the excel sheet. 
This was my first time using PowerBI, and having other projects to complete from my FRONTEND and BACKEND Development, and DIGITAL MARKETING courses (By DIGITAL AFRICA/Talent4Startups) reduced the amount of time i could've taken to complete this project.

Everything else was smooth sailing as i had previous insights from using multiple platforms and applications for compliling data, docs, presentations which are similar in use.

### PowerBI is an intuitive platform for data visualizations and ill keep on advancing my skills on it.



