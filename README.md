# An Analysis of Kickstarter Campaigns.

In this analysis, kickstarter campaigns are analyzed by category, subcategory, success rates and launch date. 
The subject for this analysis, Louise, is hoping to successfully raise enough money for her play *Fever*. She has already come close to her goal of £4,000 but she wants to understand three key issues:

- When is the best time to launch a Theater campaign.
- The success rate for plays overall.
- How the goal affects the outcome.

The raw data for that analysis can be found here - [Kickstarter_Challenge](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/Kickstarter_Challenge.xlsx)

---
## Analysis and Challenges

In order to analyze the data with Louise's campaign in mind, we organize the excel file to focus on each area she cares about. There is a lot of data to consider, so reviewing how theater campaigns perform, when they best perform and how her specific type of theater campaign - a play, performs is very helpful to understand how her current campaign is doing. Secondly, most of the data belongs to campaigns that aren't plays or even theater related. While this may seem irrelevant, it's important to see how she is doing compared to all the other Kickstarter campaigns overall, because there is reason to be optimistic.

On the technical side of things, this analysis is accomplished mostly through pivot tables and the charts generated from them.

___

### Analysis - Launch Dates

![Theater Outcomes vs Launch](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png)

Louise wants to know if there's an optimal time to launch a campaign like hers. It turns out, there definitely is an ideal time - May, June and July, which have success rate far above the norm, especially May. Conversely, she should not launch a kickstarter for a play in December, where the success rate dips down almost to the failure rate. 

The chart itself is a line graph detailing the three outcome statuses - Successful, Failure and Canceled, for each month for all Theater kickstarters, regardless of country, year, or fundraising goal. In tabular form, the data looks like this. 

<img src="https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/theater_outcomes_tabular.png" width="270" height="250">

---
### Analysis - Outcomes Based on Goals

![Outcomes Based on Goals](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Outcomes_vs_Goals.png)

Louise wants to know successful the play kickstarters with funding goals similar to hers fare overall. The above graph charts the success vs failure vs canceled rates for all kickstarter plays, broken into ranges determined by funding goals. If the chart looks like it is missing a line, it's because there were no canceled kickstarters for plays, so that line is just completely horizontal along the x-axis.
Overall, she should take comfort in that most kickstarters of her subcategory with similar funding goals ultimately succeed. 

Generally, there is a negative correlation between funding goal and success rate. As the goal becomes more expensive, the less likely the campaign is to succeed. However, there is an interesting reversal of this trend, between $35,000 and $44,999, where the success rate jumps to 67%. The reasons for this temporary reversal should be reviewed more closely. 

---
### Analysis - Successful vs Failed Kickstarter Plays

![Successful vs Failed Kickstarter Plays](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Successful_vs_Unsuccessful_Plays.png)

The above chart shows the mean number of campaigns donators and how much they donated. Interestingly, the mean donation size between successful and failed campaigns is not that much, around $17 ($89 for successful and $72 for failed campaigns). The key difference was in the number of donators. Successful campaigns had nearly 8 times as many donators as unsuccesful campaigns. This suggests that campaigns do not succeed because of large donations but rather a broad base of small-dollar contributions. Given this finding, the success vs failure rate of campaigns seems to largely depend on the campaign owner's ability to market the campaign and engage with the pool of potential donators. 

---
### Analysis - Challenges

This was a large dataset, and it did not come without issues, such as the following: 
- Descriptions in other languages
- Inconsistent currency denominations
- Invalid Characters
- Data Type Conversion Errors

---

#### Challenges - Descriptions in Other Languages

![Description in German](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Description_In_German_Screenshot.png)
![Description in French](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Description_In_French_Screenshot.png)

While these don't impede your ability to analyze the data, it's certainly annoying, especially if you are trying to analyze the content of the campaign.

---

#### Challenges - Inconsistent Currency Denominations

![British Pound](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/British%20Pound.png)

Most of the kickstarters were denominated in USD, but there were a significatn number that were either in British Pounds, Euros, Australian Dollars or others. Furthermore, when updating the data set to recognize the pledged, and goal columns, all rows show USD regardless of actual currency. 
For this particular analysis, it only became an issue in the 'Goals vs Outcome' analysis, which looked at all plays, so plays with goals in multiple currencies were grouped into one chart. 

Fortunately, the vast majority of these campaigns were from countries with similarily valued currencies. However, there were 6 plays from Mexico, and they had a mean goal of $36,833. However, if that was meant to be 36,833 Mexican Pesos, it would convert to roughly $1,823 which seems much more likely. 

This wasn't corrected, and it would be hard to accurately convert all these campaigns into one currency, all they are all floating point currencies that shift from day to day.

---

#### Challenges - Invalid Characters

![Invalid Characters](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Invalid_Characters_Screenshot.png)

This didn't affect the analysis, it's just annoying. 

---

#### Challenges - Data Type Conversion Errors

![Pound Symbol](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Pound_Symbol_Screenshot.png)
