# Kickstarter-Analysis
An Analysis of Kickstarter Campaigns

## Overview of Project

### Purpose
The purpose of this analysis was to determine how the outcome of the campaigns changed with respect to the date in which they were launched for all theaters, and how the outcome of the campaigns changed with respect to the size of their funding goal for all plays.


## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
To perform this analysis, the number of each outcome was calculated for every year for the "theater" subcategory. This was done by adding a new column to the Kickstarter sheet labeled "Year" where the YEAR() function was used to extract the year from the "launched_at" column. However, the values given in the "launched_at" are not given in a date format. In order to get these values into a date format, a new column was created and by using the formula: "=(((launced_at/60)/60)/24)+DATE(1970,1,1)" the correct date was found. Then the YEAR() function could be used to extract the year the campaign was launched. After the year was extracted, then a pivot table was created and filtered based on the "Parent Category" and "Year" fields. After the pivot table was created, then the outcomes column was filtered to show only the successful, failed, and canceled campaigns and filtered to show the columns in descending order. Then the "Row Labels" column was grouped to show the total number of outcomes for each month instead of each year. Then to find the number of outcomes for the "theater" parent category, all that needs to be done is select "theater" from the parent category drop box. The final pivot table is illustrated in the picture below. Then a graph was made plotting the number of each outcome vs. each month and is illustrated in the graph below titled, "Theater Outcomes Based on Launch Date."  

![analysis of launch date](https://user-images.githubusercontent.com/75760493/102688519-ccc43580-41bc-11eb-83f6-7995205ae457.PNG)

### Analysis of Outcomes Based on Goals
To perform this analysis, the number of each outcomes needed to be calculated for different goal sizes for the "plays" subcategory. This was done by creating a new sheet with columns for the total number of succeeded, failed, and canceled outcomes along with the total number of outcomes. Along with those columns, a column was created to differentiate between the number of outcomes based on different goal sizes. Rows were created in the Goal column for goals less than 1000, between 1000 and 4999, between 5000 and 9999, between 10000 and 14999, between 15000 and 19999, between 20000 and 24999, between 25000 and 29999, between 30000 and 34999, between 35000 and 39999, between 40000 and 44999, between 45000 and 49999, and those goals greater than 50000. Then, the number of outcomes that succeeded, failed, canceled, and total number of outcomes were calculated per goal size by using the COUNTIFS function and was done for each outcome and for each goal size. The first function would look like this "=COUNTIFS(Kickstarter!D:D, "<1000", Kickstarter!F:F, "successful", Kickstarter!R:R, "plays")" where the goal size is less than 1000 and the outcome would be successful. This formula would be changed to fit which ever goal size was used and for each individual outcome. The number of each outcome vs. each goal size is illustrated in the picture below.

After the total number of outcomes was calculated, then the percentage of each outcome was calculated per goal size. The percentage was found by dividing the number of outcomes by the total number of outcomes. The total number of outcomes was found by adding the number of successful, failed, and canceled outcomes per each goal size. To get the percentage to a whole number, the ROUND function would need to be used. So for the goal size less than 1000, the percentage of successful campaigns was found by using the following formula: "ROUND(Number of Successful Outcomes/Total Number of Outcomes, 2)." This formula was used for each outcome and for each goal size. After finding each outcomes percentage, a graph was made plotting the percentage of each outcome vs. the goal size as illustrated in the graph below titled, "Outcomes Based on Goal." 

![analysis of goals](https://user-images.githubusercontent.com/75760493/102688039-afda3300-41b9-11eb-986c-09f47e960f35.PNG)

### Challenges and Difficulties Encountered
One of the challenges I kept encountering was accurately calculating the total count of outcomes based on the amount of the funding goal. I kept getting results from my formula that weren't matching the correct results. After playing with the formula, I had realized that I was using the values in the "Pledged" column instead of the values from the "Goal" column. That error was substantial enough for me to easily see that something was wrong with my formula based on the values I was getting. 

## Results

### What are two conclusions you can draw about the Outcomes based on Launch Date?
One conclusion that can be made is that for every month, more campaigns successfully reached their goal than those that failed or canceled their fundraiser. Also, another conclusion that can be made is there was a drastic increase in campaigns that were launched in May, almost doubling the monthly average. 

### What can you conclude about the Outcomes based on Goals?
It can be concluded from the "Outcomes Based on Goals" graph that the larger the goal a campaign needs, the higher chance it has at failing; while the smaller the goal is, the higher the chance it has to succeed.

### What are some limitations of this dataset?
One limitation of this dataset is that it only gives data from 2009 to 2017. This restricts the data to only data recorded during these nine years. Another limitation is that this dataset represents data from 21 countries. This restricts the data to only data from these 21 countries and can't be used to accurately reflect the entire world.

### What are some other possible tables and/or graphs that we could create?
Another table I would like to see is how many backers did the successful campaigns have compared to the campaigns that failed. Along with that, I would also like to see the average donation each backer made to see if the reason a campaign failed had been influenced by the backers not paying as much as those backers who supported the successful campaigns. Another table of interest would be the success rate per parent category, to compare the success rate varies depending on the parent category and see which types of campaigns are the most successful in reaching their goal.
