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
Overall, she should take comfort in that most kickstarters of her subcategory with similar funding goals ultimately succeed. Generally, there is a negative correlation between funding goal and success rate. 

