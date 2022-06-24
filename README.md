# Kickstarter Analysis Project 
## Overview of Project
The purpose of this project was to compare the different campaigns based on their launch dates as well as their fundraising goals. We've analyzed data by creating pivot tables for specific parent categories and created visualization of the data by creating line plots. Moreover, we calculated the percentages of the failed, successful and canceled projects to determine how these outcomes effected the overall campaign. In this project, we will analyze how projects in categories **theater** and **plays** based on the month of their launch performed. 

Our analysis has determined there is in fact a trend between the time of the year a campaign in launched effecting its overall performance. 
## Analysis and Challenges 
### Analysis: Theater 
Let's begin with the category: theater. 

**Step 1: Determine outcomes based on Parent Categories** 

In order to help Louise with our analysis on when is the best time for campaigns to be launched, we started with the category that was the most successful throughout different countries, theater. 
Firstly, we created a pivot table of all the *Parent Categories* from our data sheet and turns out that theater was hands down the most successful in comparison with other categories like *food, music, games, journalism,etc*. The pivot table allows us to generate a specific value for our "outcomes" field, so we are able to look at the results and compare the specific category based on their count of outcomes. 

*Breakdown of the Pivot Table Fields* 

*Filters*: Country
Country will be our filter so we can analyze the data of outcomes for each parent category based on their destination. Therefore, if Louise is launching her campaign in the US, we would be able to evaluate the number of successful, failed and canceled outcomes based on the designated country. 

*Columns*: Outcomes
The "outcomes" field is put in the columns section so we can have the relevant values for each outcome right below it laid out in the appropriate cell. Our outcomes for this data includes: failed, successful and canceled. Each outcome relays important information for us to further decode our analysis. 

*Rows*: Parent Category 
Parent category is a must to include in this pivot table as it helps us to further analyze our data for theater to report to Louise in our overall report. 

*Values*: Count of outcomes 
Here, we just dragged "outcomes" to the "value" field so we are able to numerically describe our outcomes section. This will allow us to determine which category was the most successful while which one was the least. 

*Pivot Table: Parent Category Outcomes*

<img width="391" alt="Screen Shot 2022-06-23 at 8 36 49 PM" src="https://user-images.githubusercontent.com/106577074/175458370-7f42622b-e047-4c4f-9da7-f7f3b6db402d.png">

*Pivot table fields*

<img width="304" alt="Screen Shot 2022-06-23 at 8 37 02 PM" src="https://user-images.githubusercontent.com/106577074/175458544-90b29d18-4ad4-4ac6-87c1-888bbd8ea8af.png">

**Step 2: Create analysis of theater based on launch dates** 

Now, we know that theater is the most successful in campaigns throughout different countries; therefore, we will go deeper into our analysis for Louise by providing her what the trends for theater outcomes look like. We will also create another pivot table to gather our data specifically for theater based on launch dates. 

Before creating our pivot table, we have to create a new column based on data in another column. Column "j" envolopes all the dates each campaign was launched at; however, the dates are not in the format we want them to be in as they are in a unix timestamp. A new column was created "Date Created Conversion" to convert all the unix timestamps for launched dates **(column j)** into human-readable dates. Although we can do this by utilizing an epoch converter tool easily accessible online via [EpochConverterTool](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#links), we used the Year function in Excel instead. 
