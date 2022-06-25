# Kickstarter Analysis Project 
## Overview of Project
The purpose of this project was to compare the different campaigns based on their launch dates as well as their fundraising goals. We've analyzed data by creating pivot tables for specific parent categories and created visualizations of the data by creating line plots. Moreover, we calculated the percentages of the failed, successful and canceled projects to determine how these outcomes effected the overall campaign. In this report, we will analyze projects in categories **theater** and **plays** based on the month of their launch and the funds they generated.

Our analysis has determined there is in fact a trend between the time of the year a campaign is launched; therefore, effecting its overall performance. 
## Analysis and Challenges 
### Analysis: Theater 
Let's begin with the category: theater. 

**Step 1: Determine outcomes based on Parent Categories** 

In order to help Louise with our analysis on when is the best time for campaigns to be launched, we started with the category that was the most successful throughout different countries, theater. 
Firstly, we created a pivot table of all the *Parent Categories* from our data sheet and turns out that theater was hands down the most successful in comparison with other categories like *food, music, games, journalism,etc*. The pivot table allows us to generate a specific value for our "outcomes" field, so we are able to look at the results and compare the specific category based on their count of outcomes. 

**Breakdown of the Pivot Table Fields:** 

*Filters*: Country
Country will be our filter so we can analyze the data of outcomes for each parent category based on their destination. Therefore, if Louise is launching her campaign in the US, we would be able to evaluate the number of successful, failed and canceled outcomes based on the designated country. 

*Columns*: Outcomes
The "outcomes" field is put in the columns section so we can have the relevant values for each outcome right below it laid out in the appropriate cell. Our outcomes for this data includes: 

- failed 

- successful 

- canceled

Each outcome relays important information for us to further decode our analysis. 

*Rows*: Parent Category 
Parent category is a must to include in this pivot table as it helps us to further analyze our data for theater to report to Louise in our overall report. So, we are pulling data specifically for the parent category.  

*Values*: Count of outcomes 
Here, we just dragged "outcomes" to the "value" field so we are able to numerically describe our outcomes section. This will allow us to plot values on our bar graph to visually detect patterns in our data for the most affluent category.

*Fig. 1: Pivot Table: Parent Category Outcomes*

<img width="391" alt="Screen Shot 2022-06-23 at 8 36 49 PM" src="https://user-images.githubusercontent.com/106577074/175458370-7f42622b-e047-4c4f-9da7-f7f3b6db402d.png">

*Fig. 2: Pivot table fields*

<img width="304" alt="Screen Shot 2022-06-23 at 8 37 02 PM" src="https://user-images.githubusercontent.com/106577074/175458544-90b29d18-4ad4-4ac6-87c1-888bbd8ea8af.png">

**Step 2: Create analysis of theater based on launch dates** 

Now, we know that theater is the most successful in campaigns throughout different countries,we will go deeper into our analysis for Louise by providing her what the trends for theater outcomes look like. We will also create another pivot table to gather our data specifically for theater based on launch dates. 

Before creating our pivot table, we have to create a new column based on data in another column. Column "j" envelopes all the dates each campaign was launched at; however, the dates are not in the format we want them to be as they are in a unix timestamp. A new column was created "Date Created Conversion" **((column S))** to convert all the unix timestamps for launched dates **(column j)** into human-readable dates. There are two ways to do this: 

1. by utilizing an epoch converter tool easily accessible online via [EpochConverterTool](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#links) 

2. By using an Excel Formula: ((cell/60)/60)/24+DATE(1970,1,1)

**example: ((J17/60)/60)/24+DATE(1970,1,1)** 

this will convert our unix timestamp in cell J17 to a human-readable format

So, we've converted our launch dates to something easier on the eyes which we can comprehend, but we need to extract the year only from this Date Created Conversion column which is much easier than the other formula we used. To extract the year from our dates, we use the formula: **YEAR()** in a seperate column **(column U)**

**example: YEAR(S17)** = 2008

Extracting the year would allow us to group the "Row Labels" column to show the month of the year on our pivot table so we can evaluate the trends of theater outcomes based on multiple years and their corresponding month performances.

Once we've extracted all the data, we will now create our pivot table so we can pull our subset of data aside and create a visualization of that data to show Louise. Using the same steps to create our pivot table as explained in *Step 1*, the pivot table filters are shown below:

*Fig. 3:*

  <img width="349" alt="Screen Shot 2022-06-24 at 12 28 42 PM" src="https://user-images.githubusercontent.com/106577074/175655892-995dc536-7319-43ba-aa48-a31ca8bd4d1a.png">

As we want to create a visualization of the trends of theater outcomes based on their launch dates, we filtered "Years" and "Parent Category," so our data will display all the years of the launched dates categorized only by theater. Moreover, for "Rows" we selected "Date Created Conversion" so we can group the years into months which will link with their relative outcomes. Lastly, the column is arranged in descending order so the list goes from successful to canceled. The end result of using the filters is shown in Fig. 4 highlighting all the data for our outcomes based on the months they were launched.

*Fig. 4: Pivot Table: Theater outcomes based on launch dates*

<img width="349" alt="Screen Shot 2022-06-24 at 12 28 42 PM" src="https://user-images.githubusercontent.com/106577074/175657291-9a8ffcc1-979d-4180-91c5-aa29bd4d5d4d.png">

To finish off our analysis of theater outcomes, a line plot was created to provide Louise with a visual summary of the data we've extracted. Doing so, we can uncover trends in the data as a pivot table may not be the best way to describe data to others and won't allow us to uncover any patterns in the data if it exists. The visualization we chose to depict the data is a line graph as it dispays our quantitative values (outcomes) over a specified time interval (months). 

*Fig. 5: Theater Outcomes Based on Launch Date Line Plot*

![OutcomesBasedonLaunchDate](https://user-images.githubusercontent.com/106577074/175757899-69b035cd-4e32-4134-82e8-496b0588327a.png)

To summarize our analysis for Louise, our line plot reveals that the best time to launch a campaign for the theater category is summer, but May specifically. The rate of successful vs canceled shows in the month of May seem to correlate well with one another as successful rates are higher while canceled and failed rates are much lower. 

### Analysis: Plays 

Now that we have our visualization for the most successful launch dates for the theater category, we need to dig deeper by visualizing the data based on percentages of our outcomes in relation to their funding goal. The subcategory we will use that lies within theater are "plays." By calculating the percentage of successful, failed and canceled plays will allow us to understand the data from a financial point of view to speculate if they met the funding goal of the overall campaign. 

In order to do this, we will use the **COUNTIFS()** function that applies criteria to cells across multiple ranges and counts the number of times all the criteria met. To use this functoin, we will be creating a new column of goal-amount ranges so projects can be grouped based on their goal amount. Then, the percentage of outcomes will determine which projects were successful and how many failed in acheiving their funding goals. 
Our goal amounts ranged from less than 1,000 all the way to 50,000 or more with increments of 4999 between each amount. Once we have the numbers isolated for how many successful, failed and canceled plays met their funding goal fallen into a specific goal-amount category, we then continued to calculate the percentage for each outcome by rounding a specific cell by the total projects.

Figure 6 displays how our datasheet looks like when we pulled data of the number of failed, successful and canceled plays that met their intended funding goals by using the **COUNTIFS()** function. After pulling aside the specific criteria of data we wanted, then we took the **SUM()** of the cells across the rows to calculate the total projects which allows us to then calculate the overall percentage of each outcome by using the **ROUND()** function.

*Fig. 6* 

<img width="989" alt="Screen Shot 2022-06-24 at 10 28 15 PM" src="https://user-images.githubusercontent.com/106577074/175759711-b00d0609-72ad-4e37-8371-fec64080d032.png">

Calculating the **COUNTIFS()** was definetly an overall challenge, but we will get to that later in the report. We want the data pulled from our original spreadsheet so we can create a visual of the outcomes based on their funding goals which will help us give Louise a confident answer if we can explain and communicate the hidden patterns within the data provided. 

Figure 7 depicts how unpredictable data can be. We can see the number of successful outcomes that reached their goal by 76% were in the range from less than 1000 while failed projects reached their funding goal by 80% in the range from 25000 to 29999. Meaning, successful projects with a lower funding goal didn't have many factors at play or expectations so they were easily close to reaching their funding goal. However, as we start going higher on our number ranges for funding goals, we start to see a trend forming -> successful percentages start to decrease in reaching their funding goals while failed percentages increase. 

*Fig. 7: Outcomes based on goal*

![OutcomesBasedonGoal](https://user-images.githubusercontent.com/106577074/175760750-38406c6b-b32c-46d2-9cfd-ed44389cc014.png)

### Challenges 

There were quite a few challenges while performing these analyses. Firstly, when creating the pivot table for theater outcomes, it took me a while to understand why we had to extract the year from the dates to get to the months. Our data consisted of campaign launches from various different years and we needed to take all of that data and compile it into an organized, easy to read chart. Therefore, extracting the year would allow Excel to group together the data from various years and summarize it according to the corresponding month. Once I took my time to understand the concept of why we are extracting the data, then reading the graph made it that much easier! I'm able to explain and understand the graph in my analysis by having identified the systemic patterns. 

Another challenge I came across while doing this assignment was calculating COUNTIFS(). I got why we grouped together the dollar-amount range for the "goals" column, but was having a difficult time actually performing the COUNTIFS() function itself. Once I started to dissect the countifs formula within each cell, I started to understand the concept a bit more and the filters started to make sense as well. I also looked at a few Youtube videos to help me further understand how to perform this function and my favorite one is linked below:

[How to Use the COUNTIF Function in Excel](https://www.youtube.com/watch?v=ZUpi52TZfCY)

Moreover, cleaning up the line graph was also a challenge I came across and took me a while to resolve it. Basically, I played around with the graph options for hours (yes, hours) and once I started to navigate the design tab and options on the graph itself, it started to look cleaner and exactly like what we had in the Challenge Module. 

Overall, many of these challenges were overcome by going back to the Canvas modules, looking at countless articles and Youtube videos and just to stay determined through every step by not giving up, but working hard to resolve the situation. 

## Results 

### Theater Based on Launch Date

The purpose of this assignement was to create visuals about campaign launches for our friend Louise to help her see the trends from the numerous amount of data provided. Firstly, we can come to the conclusion based on the "Theater Outcomes by Launch Date" line plot that the best time to launch campaigns is during the month of May with more successful outcomes vs failed.Secondly, the only time the number of failed and successful outcomes were almost even was in Decemeber, which makes sense as those are the holidays and most people spend them at home with their loved ones. 

### Outcomes Based on Goal 

Moving along, based on the "Outcomes Based on Goal" line plot, we had to financially determine which projects brought in the most revenue closest to their funding goal. What's interesting here is that the percentage of failed projects seem to be closer to their funding goal more than the percentage of successful projects, especially when we get farther down the plot to the higher goal-amount ranges. What's even more interesting about this visual from our analysis on funding goals is that the lines are mirroring one another. They intersect three times on the plot before going their opposite directions correlating with one another. 

### Conclusion 

Even though we provided a visual analysis on theater and its subcategory plays, we need to keep in mind that this isn't sufficient for providing our overall analysis about what is the best time to launch campaigns. This information is conlcuded from only a subset of the mass amount of data we have, but there are so many more parts to launching a campaign. To further strengthen our analysis we should repeat the same process of creating pivot tables and line graphs for other categories and their subcategories form the campaign to see if the trends we have seen with theater/plays is the same throughout the board. That way, we can confidently go to Louise and give her our answer about when is the best time to launch campaigns.
