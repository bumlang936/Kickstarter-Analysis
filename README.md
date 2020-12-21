# Kickstarter-Analysis
An Analysis of Kickstarter Campaigns

## Overview of Project

### Purpose
The purpose of this analysis was to determine the outcome of the campaigns changed with respect to the date in which they were launched, and with respect to the size of their funding goal.


## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
In order to perform this analysis, the number of each outcome was calculated for every year for the "theater" subcategory. This was done by adding a new column to the Kickstarter sheet labeled "Year" where the YEAR() function was used to extract the year from the launch date coulmn. After the year was extracted, then a pivot table was created and filtered based on the "Parent Category" and "Year" fields. After the pivot table was created, then the outcomes column was filtered to show only the successful, failed, and canceled campaings and also filtered to show the columns in descending order. Then the "Row Labels" column was grouped to show the total number of outcomes for each month instead of each year. Then in order to find the number of outcomes for the "theater" parent category, all that needs to be done is select "theater" from the parent category dropbox. The final pivot table is illustrated in the picture below. Then a graph was made plotting the number of each outcome vs. each month and is illustrated in the picture below. 

![analysis of launch date](https://user-images.githubusercontent.com/75760493/102688519-ccc43580-41bc-11eb-83f6-7995205ae457.PNG)

### Analysis of Outcomes Based on Goals
In order to perform this analysis, the number of each outcomes needed to be calculated for different goal sizes for the "plays" subcategory. This was done by creating a new sheet with columns for the total number of succeeded, failed, and canceled outcomes along with the total number of outcomes. Along with those columns, a column was created to differentiate between the number of outcomes based on different goal sizes. Rows were created in the Goal column for goals less than 1000, bewtween 1000 and and 4999, between 5000 and 9999, between 10000 and 14999, bewteen 15000 and 19999, between 20000 and 24999, between 25000 and 29999, between 30000 and 34999, between 35000 and 39999, bewteen 40000 and 44999, between 45000 and 49999, and those goals greater than 50000. Then, the number of outcomes that succeeded, failed, canceled, and total number of outcomes were calcluated per goal size by using the COUNTIFS function and was done for each outcome and for each goal size. The first function would look like this "=COUNTIFS(Kickstarter!D:D, "<1000", Kickstarter!F:F, "successful", Kickstarter!R:R, "plays")" where the goal size is less than 1000 and the outcome would be successful. This formula would be changed to fit which ever goal size was used and for each individual outcome. The number of each outcome vs. each goal size is illustrated in the picture below.

After the total number of outcomes was calculated, then the percentage of each outcome was calculated per goal size. The percentage was found by dividing the number of outcome by the total number of outcomes. The total number of outcomes was found by adding the number of successful, failed, and canceled outcomes per each goal size. In order to get the percentage to a whole number, the ROUND function would need to be used. So for the goal size less than 1000, the percentage of successful campaigns was found by using the following formula: "ROUND(Number of Successful Outcomes/Total Number of Outcomes, 2)." This formula was used for each outcome and for each goal size. After finding each outcomes percentage, a graph was made plotting the percentage of each outcome vs. the goal size as illustrated in the picture below. 

![analysis of goals](https://user-images.githubusercontent.com/75760493/102688039-afda3300-41b9-11eb-986c-09f47e960f35.PNG)

### Challenges and Difficulties Encountered
One of the challenges I kept encountering was accurately calculating the total count of outcomes based on the amount of the funding goal. I kept getting results from my formula that weren't matching the correct results. After playing with the formula, I had realized that I was using the values in the "Pledged" column instead of the values from the "Goal" column. That error was substantial enough for me to easily see that something was wrong with my formula based on the values I was getting. 

## Results

### What are two conclusions you can draw about the Outcomes based on Launch Date?
One conclustion that can be made is that for every month, more campaigns successed reaching their goal than those that failed or canceled their fundraiser. Also, another conclustion that can be made is there was a drastic increase in campaigns that were launched in May, almost doubling the monthly average. 

### What can you conclude about the Outcomes based on Goals?
It can be concluded from the "Outcomes based on Goals" graph that the larger the goal a campaign needs, the higher chance it has at failing; while the smaller the goal is, the higher the chance it has to succeed.

### What are some limitations of this dataset?
One limitation of this dataset is that it only gives data from 2009 to 2017. This restricts the data to only data recorded during these nine years. Another limitation is that this dataset represents data from 21 countries. This restricts the data to only data from these 21 countries and can't be used to accuratley reflect the entire world.

### What are some other possible tables and/or graphs that we could create?
Another table I would like to see is how many backers did the successful campaigns have compared to the campaigns that failed. Along with that, I'd also like to see the average donation each backer made to see if the reason a campaign failed had been influenced by the backers not paying as much as those backers who supported the successful campaigns. Another table of interest would be the success rate per parent category, to compare the success rate varies depending on the parent category and see which types of campaigns are the most successful in reaching their goal.
