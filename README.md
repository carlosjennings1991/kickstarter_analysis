# An Analysis of Kickstarter Campaigns.

In this analysis, Kickstarter campaigns are analyzed by category, subcategory, success rates and launch date. 
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

Louise wants to know if there's an optimal time to launch a campaign like hers. It turns out, there definitely is an ideal time - May, June and July, which have success rate far above the norm, especially May. Conversely, she should not launch a Kickstarter for a play in December, where the success rate dips down almost to the failure rate. 

The chart itself is a line graph detailing the three outcome statuses - Successful, Failure and Canceled, for each month for all Theater Kickstarters, regardless of country, year, or fundraising goal. In tabular form, the data looks like this. 

<img src="https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/theater_outcomes_tabular.png" width="270" height="250">

---
### Analysis - Outcomes Based on Goals

![Outcomes Based on Goals](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Outcomes_vs_Goals.png)

Louise wants to know successful the play Kickstarters with funding goals similar to hers fare overall. The above graph charts the success vs failure vs canceled rates for all Kickstarter plays, broken into ranges determined by funding goals. If the chart looks like it is missing a line, it's because there were no canceled Kickstarters for plays, so that line is just completely horizontal along the x-axis.
Overall, she should take comfort in that most Kickstarters of her subcategory with similar funding goals ultimately succeed. 

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

Most of the Kickstarters were denominated in USD, but there were a significant number that were either in British Pounds, Euros, Australian Dollars or others. Furthermore, when updating the data set to recognize the pledged, and goal columns, all rows show USD regardless of actual currency. 
For this particular analysis, it only became an issue in the 'Goals vs Outcome' analysis, which looked at all plays, so plays with goals in multiple currencies were grouped into one chart. 

Fortunately, the vast majority of these campaigns were from countries with similarily valued currencies. However, there were 6 plays from Mexico, and they had a mean goal of $36,833. However, if that was meant to be 36,833 Mexican Pesos, it would convert to roughly $1,823 which seems much more likely. 

This wasn't corrected, and it would be hard to accurately convert all these campaigns into one currency, all they are all floating point currencies that shift from day to day.

---

#### Challenges - Invalid Characters

![Invalid Characters](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Invalid_Characters_Screenshot.png)

This didn't affect the analysis, it's just annoying. 

---

#### Challenges - Data Type Conversion Errors

![Data Conversion](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Data%20Conversion.png)

This was very frustrating at first, because these two columns were used in generating two other columns of the data sheet. However, simply changing the data type from 'Time' to 'Number' solved the issue. 

---
## Results

This analysis led a few key findings and a couple dead-ends. While the case study, Louise, should feel optimistic about being able to successfully reach her goal, the data set is slightly flawed due to an issue regarding currency conversions. Secondly, 'Theater' as a broad category performs well overall, and while 'Plays' don't perform quite as well as its parent category, plays still outperform Kickstarter campaigns writ large. Just to give a snapshot of this, the chart below plots plays against film & video, tech and games.

![Outcomes Across 4 Categories](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Outcomes_Across_Categories.png)

As you can see, Plays do very well. There has to be a reason for this overperformance, and I believe it boils down to two variables:

* Location of the Plays
* The people running the Campaign

Plays are location specific and they require a large crew of actors and technicians. Because they are location specific, they have an intrinsic community identity. Supporting your local theater has a greater community impact than supporting a game or tech idea. 

Secondly, plays require a lot of people. Each one of those persons has a network of people they can ask for a donation. Even though the crew techs and actors may not be running the Kickstarter campaign, they can still help out. Plays may have a built-in advantage since they can cast a wider net of potential supporters. 

Thirdly, this overperformance might come down to personality type. The theater tends to belong to people with big, charismatic personalities. It takes a lot of guts to get on stage and perform in front of strangers. By this logic, the same people might be better at asking for donations vs those working in other non-theater related campaigns. **However this cannot be proven and is purely conjecture.**

There are a few concrete takeaways that are proven by the data, and they are detailed below.

---

### Results - Theater Outcomes Are Influenced By Launch Date

![Theater Outcomes vs Launch](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png)

Outcomes are significantly affected by launch date, a fact concretely proven in the data. This conclusion contains three key takeaways. 

* May, June and July have success rates well above average.
* May is the best month to launch a play.
* December is the worst month to launch a play.

---
### Results - Goals do effect Outcomes

![Outcomes Based on Goals](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Outcomes_vs_Goals.png)

The second major finding is that the funding goals do affect outcomes, and provide two additional conclusions.

* There is generally a negative correlation between funding goal and success, i.e the higher the funding goal, the less likely the campaign is to succeed. 
* There is a temporary reversal of this trend between $35,000 and $44,999. 

---
### Results - Limitations within the Dataset

While the dataset contains a lot of data, it is slightly flawed for two reasons. 

* Inconsistent currency conversions
* Inconsistent labeling

The first flaw is detailed earlier in this analysis. The second flaw, inconsistent labeling, shows up across the data set and it is difficult to isolate the effected rows from the rest of the data. However, just a cursory glance yields a few examples. For instance, the screenshot below shows a TV kickstarter, that describes itself as Sci-Fi/Science Fiction. Even though there is a 'Science Fiction' subcategory within Film & Video, it looks to only apply to Movies that are Science Fiction. 

* TV show example. 

![Confusing Labeling](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Confusing%20Labeling.png)

* Movie Example.

![Confusing Labeling_2](https://github.com/carlosjennings1991/kickstarter_analysis/blob/main/resources/Confusing%20Labeling_2.png)

It would be extremely difficult to isolate inconsistent labeling, so it could be an extensive problem or the above examples could be an edge case. 

---
### Results - Recommendations

While the data includes a lot of great information that can inform the decisions for Louise and those like her, it leaves a lot to be desired. For one, it would be helpful to have the following as columns in the data set. 

* If the owner has done a Kickstarter before.
* If they have, if it was successful.
* Number of people running the Kickstarter.
* Campaign owner's occupation.
* Campaign owner's age. 
* Campaign owner's social media platforms. 
* Campaign owner's following on social media. 
* Campaign owner's location
* Number of people involved in campaign.

Here is why those 8 criteria would be important. They would go a long way in explaining how the campaign owners ran their Kickstarters.
For example, Theater performs very well as a category compared to the rest of the Kickstarter data set. The subcategory of Plays performs similarly well. This has to be explained by data not found in the data set. This discrepency could be due to the following. 

* Those running Theater campaigns have the skills to better promote their campaign compared to the rest of Kickstarter. 
* They might have large social networks they could draw upon for support. 
* They might skew younger and one can infer they might have better tech/marketing skills. 
* Theater kickstarters might have a lot of people involved even if they aren't necessarily the campaign owner. 
* Location would explain a lot, like if a campaign is for a community theater project in a wealthy area.

---

### Results - Conclusions

Ultimately, the data set provides some interesting data, most notably in regards to time, funding goals, and category performance. However, these metrics only shed light on the outcome. There is little to explore how the campaign owners run their campaigns. More info on the people running the Kickstarters would help inform the mechanics of running a successful campaign. 


