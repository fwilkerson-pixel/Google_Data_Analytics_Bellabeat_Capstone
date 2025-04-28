# Bellabeat Capstone Case Study

##### Author: F. Wilkerson
##### Date: 02/20/2025

## Table of Contents
[Introduction](#introduction)<br/>
[Business Task](#business-task)<br/>
[Stakeholders](#stakeholders)<br/>
[Data Overview](#data-overview)<br/>
[Data Processing](#data-processing)<br/>
[Data Exploration and Visualization](#data-exploration-and-visualization)<br/>
[Conclusions and Recommendations](#conclusions-and-recommendations)

## Introduction
[Back To Top](#bellabeat-capstone-case-study)
<br/><br/>
Founded in 2013, Bellabeat is a health-focused, high-tech company that designs smart wellness products specifically for women. While Bellabeat has found success as a small player in the market, it has the potential to expand its footprint in the growing global smart device industry.

In this case study, I was tasked with analyzing external smart device usage data to uncover patterns and trends in consumer behavior. The goal of this analysis is to generate actionable insights that can inform Bellabeat’s marketing strategy and support data-driven decision-making.

The findings and recommendations presented here are intended for Bellabeat’s executive team, providing a strategic overview that can help the company better position itself in a competitive, health-conscious market.
<br/><br/>

**Additional Information About Bellabeat:**
* Collecting data on activity, sleep, stress, and reproductive health has allowed Bellabeat to empower women with knowledge about their own health and habits.

* By 2016, Bellabeat had opened offices around the world and launched multiple products.

* Bellabeat’s products are available through a growing number of online retailers and their own e-commerce channel on their website.

* Current Marketing Strategies:
  * The company focuses on digital marketing extensively. Bellabeat invests year-round in:
    * Google Search 
    * Maintaining active Facebook and Instagram pages, and consistently engages consumers on Twitter. 
    * Bellabeat runs video ads on Youtube and display ads on the Google Display Network to support campaigns around key marketing dates.

  * The company has invested in traditional advertising media, such as radio, out-of-home billboards, print, and television
<br/><br/>

## Business Task
[Back To Top](#bellabeat-capstone-case-study)
<br/><br/>
The goal of this project is to analyze current trends in smart health device usage and provide high-level, data-driven recommendations to support Bellabeat’s marketing strategy. These insights will specifically inform strategic planning for the Bellabeat mobile app, helping the company better engage users and promote wellness through personalized digital experiences.
<br/><br/>

## Stakeholders
[Back To Top](#bellabeat-capstone-case-study)
<br/><br/>
**Primary Stakeholders:** 
  * Urška Sršen: Bellabeat co-founder and Chief Creative Officer
  * Sando Mur: Bellabeat co-founder

**Secondary Stakeholders:** 
 * Bellabeat marketing analytics team
 <br/><br/>
 
## Data Overview
[Back To Top](#bellabeat-capstone-case-study)
<br/>
### Data Source
The dataset used in this analysis is publicly available [FitBit Fitness Tracker data](https://www.kaggle.com/datasets/arashnic/fitbit), shared by Mobius on Kaggle. It contains anonymized user information, including daily physical activity, sleep patterns, and heart rate data.  The original dataset was created by Furberg, Robert; Brinton, Julia; Keating, Michael; and Ortiz, Alexa, and is available on Zenodo:  [https://zenodo.org/record/53894#.YMoUpnVKiP9](https://zenodo.org/record/53894#.YMoUpnVKiP9)

The data was collected through a distributed survey conducted via Amazon Mechanical Turk between 03.12.2016-05.12.2016. A total of thirty eligible Fitbit users voluntarily consented to share their personal tracker data for the purposes of this study.

### Data Limitations
While the dataset provides valuable insights into user behavior with Fitbit smart devices, there are several important limitations to consider:

**Source and Collection Method:**
The data was self-reported by participants recruited via Amazon Mechanical Turk (MTurk). This platform tends to attract a specific demographic—typically younger, more tech-savvy individuals—which may introduce selection bias. Additionally, responses were collected over a short time frame, providing only a limited snapshot of user activity.

**Sample Size:**
Only 30 eligible Fitbit users consented to the submission of their personal activity data. This small sample size limits the statistical power of the analysis and may not fully represent the diversity of the broader smart device user base.

While the sample size of 30 meets the common minimum threshold for certain types of statistical analysis, it results in a relatively large margin of error. Using a population estimate of 50 million Fitbit users in 2016 and a 90% confidence level, the margin of error for this sample is approximately ±15.07%.

To reduce the margin of error to a more acceptable ±5%, a sample size of at least 273 participants would have been required. 

**Data Authenticity and Precision:**
Because the dataset is based on self-submitted data rather than data pulled directly from Fitbit’s internal systems, there may be inconsistencies or inaccuracies due to incomplete tracking or user error.

**Temporal Relevance:**
The data is from 2016, which presents a potential mismatch with current consumer behaviors and trends in 2025. Technological advances, user expectations, and health and wellness habits have likely evolved since the data was collected.
 <br/><br/>

**Despite these limitations**, I approached the analysis with careful consideration of context. Where possible, I avoided overgeneralizing and focused on **broad behavioral patterns** rather than definitive metrics. The insights and recommendations are framed with an understanding of the dataset’s constraints and should be viewed as directional rather than precise, real-time predictions.
 <br/><br/>

## Data Processing
[Back To Top](#bellabeat-capstone-case-study)
<br/>
### Clean and Examine Data in Google Sheets
Initial data cleaning was conducted in Google Sheets to ensure accuracy and consistency prior to deeper analysis:

* Conditional formatting was applied to identify blank or missing cells for further review.
* When importing the dataset, the option to automatically convert numeric values was enabled to ensure numeric fields were properly recognized.
* Duplicate rows were identified and addressed using the Data → Data Cleanup tool.
* To verify the validity of date fields, a custom conditional formatting formula was used: =ISDATE([range]). 

While **date conversion** was ultimately performed during the exploration phase (see below), I recognize that handling date formatting at this early stage would have improved workflow efficiency. This is a noted improvement for future analyses.
<br/><br/>

### Examine Data in RStudio
<br/>

<ins>**Installing Packages & Loading Libraries**</ins>

![image](https://github.com/user-attachments/assets/2cd98e45-ddc6-4a22-ade6-d83240199a90)
<br/><br/>

<ins>**Import CSV Files**</ins>
<br/>

Sample...<br/><br/>
![image](https://github.com/user-attachments/assets/a7b27dc5-687c-490c-87d6-01b0ead18b2f)
<br/><br/>

<ins>**Data Examination**</ins>
<br/><br/>
To obtain an additional overview of the dataset, the head(), glimpse() and colnames() functions were used in RStudio to examine the structure of the data and identify available variables.

Sample...<br/><br/>
***daily_activity***

![image](https://github.com/user-attachments/assets/973dbb48-0581-437d-a865-2779cebca5cc)
![image](https://github.com/user-attachments/assets/6f7c918e-335a-4551-a09d-cae6eca031c4)
![image](https://github.com/user-attachments/assets/edd2ef81-005a-4536-89c2-a225f41f0394)

***sleep_day***

![image](https://github.com/user-attachments/assets/2b61af03-61d8-4457-857f-6ec8ba7d8457)
![image](https://github.com/user-attachments/assets/76de451c-1c97-46de-a81f-7addcf5fc81e)

***hourly_intensity***

![image](https://github.com/user-attachments/assets/7afa02f8-f80c-4f4d-b62b-ad6f4305f20f)
<br/><br/>

<ins>**Check Number of Unique Participants**</ins>
<br/>

Sample...<br/><br/>
![image](https://github.com/user-attachments/assets/07b33124-16cc-481b-9e37-d3974b4ee4d3)

**Discovery:** Some participants do not have data in the sleep_day dataset
<br/><br/>

<ins>**Number of Observations/Rows**</ins>
<br/>

Sample...<br/><br/>
![image](https://github.com/user-attachments/assets/3fc0cd52-567b-4333-a90b-362210fb9ba5)
<br/><br/>

<ins>**Quick Summary**</ins>

Sample...<br/><br/>
<ins>***daily_activity***</ins>

![image](https://github.com/user-attachments/assets/d69b1df2-ed31-40e1-b96f-e419132bc2da)

<ins>***sleep_day***</ins>

![image](https://github.com/user-attachments/assets/6e543740-73f0-4cb7-a01a-ab152bd47628)

<ins>***hourly_intensity***</ins>

![image](https://github.com/user-attachments/assets/2add441f-ab58-4a55-86ff-02d02e2ef0e8)
 <br/><br/>
 
## Data Exploration and Visualization
[Back To Top](#bellabeat-capstone-case-study)
<br/>
### Total Steps VS Sedentary Minutes
![image](https://github.com/user-attachments/assets/b254cf09-22d4-4edf-a339-e66f22c38384)
<br/><br/>
![image](https://github.com/user-attachments/assets/c6aff2b1-21bd-46b1-a9ca-7bdcbc23da80)
![image](https://github.com/user-attachments/assets/1e736c13-461d-4852-94ac-09e8cb79f10f)
<br/><br/>
**Assessment:**
* There is a moderate negative correlation between Total Steps and Sedentary Minutes. Correlation Coefficient (r = –0.33); p-value < 2.2e-16, This is highly statistically significant — way below the 0.05 threshold, In other words: The relationship between steps and sedentary time is very unlikely to be due to chance; Confidence Interval: [-0.383, -0.269]. We are 95% confident that the true correlation lies between –0.38 and –0.27.  This reinforces that the effect is consistently negative, not a fluke.

* The correlation between Total Steps and Sedentary Minutes: r = –0.33
  * This means: As people take more steps, they generally spend less time being sedentary. This makes intuitive sense — higher step counts = less time sitting
  * However, this is a **moderate** negative correlation. It is not weak, but it is not strongly inverse either.
    * If the correlation were strongly negative (say, r = –0.8), that would suggest: "Users who walk a lot almost never sit for long."
    * But with r = –0.33, we’re seeing: "Users who take more steps tend to sit less — but not dramatically so."
  * This moderate inverse relationship suggests users may engage in bursts of movement while still spending much of the day sedentary — consistent with patterns like office work or structured workouts."  
  * To confirm, I will chart 'Activity Percentages By Activity Intensity', 'Distribution of Active Minutes by Hour' AND 'Top High Intensity Workout Hours'.
  * If confirmed, this information could be used to target computer/desk workers, students, anyone who is sitting most of the day to get them to add more steps in their day instead of single burst of workout activity. 
<br/><br/>

### Activity Minutes By Activity Intensity
![image](https://github.com/user-attachments/assets/b185861b-e6a0-4350-8419-43243b4d24f3)
![image](https://github.com/user-attachments/assets/3eca0ae2-e96a-4f78-8796-c1c5a1bb2741)
<br/><br/>
![image](https://github.com/user-attachments/assets/307bbd82-82a6-4277-810c-8717a825fa79)
<br/><br/>
**Assessment:**
* Most minutes are spent being sedentary
* This supports the hypothesis in the section "Total Steps VS Sedentary Minutes, that users spend more time sedentary than active
<br/><br/>

### Distribution of Active Minutes by Hour
![image](https://github.com/user-attachments/assets/8c7054c8-2bc4-46b2-ac25-782c0a29f34d)
<br/><br/>
![image](https://github.com/user-attachments/assets/8092397b-ebf1-4725-97a8-b8b41c4ee760)
<br/><br/>
**Assessment:**
* Morning spike around 7–9 AM

* Evening peak from 5–8 PM

* A small midday burst near noon

* This supports the hypothesis in the section "Total Steps VS Sedentary Minutes, that users engage in bursts of movement while still spending much of the day sedentary — consistent with patterns like office work. This information could be used to target computer/desk workers (office/remote workers), students, anyone who is sitting most of the day to get them to add more steps in their day.

* This also fits with known user behavior from health studies & wearables:
  * Morning workout → Sit at desk all day
  * Evening run → Sedentary most of the day
    * Brickwood, K. J., Watson, G., O'Brien, J., & Williams, A. D. (2019). Consumer-based wearable activity trackers increase physical activity participation: Systematic review and meta-analysis. JMIR mHealth and uHealth, 7(4), e11819. https://doi.org/10.2196/11819
<br/><br/>

### Top High Intensity Workout Hours
![image](https://github.com/user-attachments/assets/ae8fea27-6620-40ac-b0ca-2028a90a1672)
<br/><br/>
![image](https://github.com/user-attachments/assets/e9dc6a61-00be-4a56-b55f-2df5921b934c)
<br/><br/>
**Assessment:**
* The most high intensity workout hours across all users were:
  * 5–7 PM suggesting after-work activity
  * 12–2 PM also show strong midday activity bursts
    
* In contrast, early morning (before 6 AM) and late night (after 9 PM) had very few high intensity workout periods.
  
* The spikes support the hypothesis, in the section "Total Steps VS Sedentary Minutes, that users engage in bursts of movement while still spending much of the day sedentary — consistent with patterns like office work. This information could be used to target computer/desk workers (office/remote workers), students, anyone who is sitting most of the day to get them to add more steps in their day. This information could be used to target computer/desk workers, students, anyone who is sitting most of the day to get them to add more steps in their day.

* These high peak times can also be an opportunity to market to people when they are most active on their phones tracking stats during high intensity workouts.
<br/><br/>

### Top Moderate to Intense Workout Hours
![image](https://github.com/user-attachments/assets/6d9615bd-3790-4c43-9b07-c5d6335f9318)
<br/><br/>
![image](https://github.com/user-attachments/assets/7aa3d221-6c66-4e88-b0a7-e2f03dcc2396)
<br/><br/>
**Assessment:**
* The most active workout hours across all users were:
  * 6–8 PM (peaking at 6 PM with 362 workouts)
  * 5–6 PM and 7–8 PM are also high, suggesting after-work activity
  * 12–2 PM also show strong midday activity bursts
    
* Early morning (before 6 AM) and late night (after 9 PM) had very few workout periods.

* The spikes support the hypothesis, in the section "Total Steps VS Sedentary Minutes, that users engage in bursts of movement while still spending much of the day sedentary — consistent with patterns like office work. This information could be used to target computer/desk workers (office/remote workers), students, anyone who is sitting most of the day to get them to add more steps in their day. This information could be used to target computer/desk workers, students, anyone who is sitting most of the day to get them to add more steps in their day.

* These high peak times can also be an opportunity to market to people when they are most active on their phones tracking stats during high intensity workouts.
<br/><br/>

### Top High Intensity Workout Days
![image](https://github.com/user-attachments/assets/1f6be26c-0249-431c-a462-f679de13a959)
<br/><br/>
![image](https://github.com/user-attachments/assets/9760a38c-11dc-47bd-90f1-f78a346f4453)
<br/><br/>
**Assessment:**
* Average Very Active Minutes — highest on Monday and Tuesday.

* There is an opportunity to market to people on Monday and Tuesdays from 12-2pm and 6-8pm when they are most likely to be on their phones tracking their activity

* There is an opportunity to start Challenges during these times as well
<br/><br/>

### Hourly Step Recording Activity
![image](https://github.com/user-attachments/assets/7998d0fa-9174-4721-856b-ff365a93096f)
<br/><br/>
![image](https://github.com/user-attachments/assets/7cf99d24-e119-47e3-b31e-bed5a4b7fea4)

<br/><br/>
**Assessment:**
* Steady rise starts around 6 AM

* Peaks during mid-morning to early evening 

* Drops sharply after 9 PM, nearly flat overnight

* This visual shows that users are consistently wearing their devices across most waking hours, with natural dips during sleep.

* Fitbit will track overnight whole body movement in bed (shifting, etc) as steps

* Users are consistently wearing their devices throughout the entire day and night — not just for workouts. These devices are deeply integrated into their routines. Opportunity to market as 24/7 health tracking or Always-on wellness insights
<br/><br/>

### Time In Bed VS Total Time Asleep
![image](https://github.com/user-attachments/assets/1fee6378-39c8-4e80-8463-883500e2965c)
<br/><br/>
![image](https://github.com/user-attachments/assets/0c7a48a5-8e47-49f0-8ef1-3ba138fd5bb9)
![image](https://github.com/user-attachments/assets/30995fd2-e1f1-401a-ba9d-c73c08a00506)
<br/><br/>
**Assessment:**
* The relationship between minutes asleep and time in bed: When users spend more time in bed, they generally get more sleep.

* This correlation is strong. Correlation coefficient (r = 0.93) This indicates a very strong positive correlation between TotalMinutesAsleep and TotalTimeInBed. The more time a user spends in bed, the more time they tend to spend actually sleeping. An r-value this high suggests the two variables move nearly in sync; p-value < 2.2e-16 Extremely statistically significant. There’s almost no chance that this correlation occurred randomly; 95% Confidence Interval: [0.916, 0.942]. This tells us that the true correlation is very likely between 0.92 and 0.94. That’s consistently very strong no matter how you slice the data

* This can also demonstrate that people are tracking their sleep activity. although using the fact that 24 unique users out of 33 total or 72.7% tracked their sleeping data is a better demonstration of this. Both can be used to demonstrate that “User behavior shows high engagement with sleep tracking features — users are not only wearing their devices at night but are generating structured, consistent sleep data. This reflects widespread interest in tracking and improving sleep quality.

* Other backup data include: 95.8% of users with sleep data logged more than one night and on average, each user logged about 17 nights of sleep.

* “User behavior shows high engagement with sleep tracking features — users are not only wearing their devices at night but are generating structured, consistent sleep data. This reflects widespread interest in tracking and improving sleep quality.”

* This information could be used to position your device as a sleep optimization coach, not just a passive tracker

* Position devices as holistic health tools, not just fitness trackers.

* Promote smart sleep features (e.g., recovery suggestions, bedtime reminders) in campaigns.
<br/><br/>

### Calories Burned VS Sleep Efficiency
![image](https://github.com/user-attachments/assets/6bb25cd9-9469-4a15-bf03-d506f03f25d2)
![image](https://github.com/user-attachments/assets/23bf0d3a-6b75-4cd9-93c7-2056b15b0e76)
<br/><br/>
![image](https://github.com/user-attachments/assets/70650011-0b5a-417e-9b8b-b7b31237f621)
![image](https://github.com/user-attachments/assets/11556d6c-2c8b-4b35-ba0b-f8cbd2b843da)
<br/><br/>
**Assessment:**
* There’s a moderate positive trend: higher calorie expenditure is generally associated with more efficient sleep.

* This supports the idea that physical activity may help improve sleep quality, which can be used as a wellness feature highlight.

* Correlation Coefficient is 0.29 with a p-value = 1.14e-09 (Statistically significant (way below 0.05) showing that this correlation is very unlikely to be due to chance). Also we can be 95% confident the true correlation lies between 0.20 and 0.38

* This supports marketing claims like: “More active days could contribute to better sleep quality.”
<br/><br/>

## Conclusions and Recommendations
[Back To Top](#bellabeat-capstone-case-study)
<br/>
### Conclusions
* Users engage in bursts of movement while still spending much of the day sedentary - consistent with patterns like computer/desk work (e.g office/remote worker or student)
 
* Workout Activity spikes occured during the following times: (Total Intensity > 20 - Moderately Active and higher)
  * Small midday burst near noon
  * Evening peak from 5 - 8 PM
 	
* The top high intensity workout hours were: (Total Intensity > 60 -  High intensity workouts only)
  * 5-7 PM suggesting after-work activity
  * 12-2 PM showing strong midday activity bursts, suggesting workouts during lunch
  	
* In contrast, early morning (before 6 AM) and late night (after 9 PM) had very few high intensity workout periods.

* Very Active Minutes where highest on Monday and Tuesday.

* Users are consistently wearing their devices throughout the entire day and night — not just for workouts. These devices are deeply integrated into their routines.
  
* User behavior shows high engagement with sleep tracking features — users are not only wearing their devices at night but are generating structured, consistent sleep data. This reflects widespread interest in tracking and improving sleep quality.

* Higher calorie expenditure is associated with more efficient sleep.


### Recommendations
* Create app notifications for office/remote works and students. Inactivity reminders and smart nudges can target the most common times these users are sedentary during the day. This will motivate them to stay consistently active throughout the day. (e.g. every hour get up and walk a flight of stairs)
Marketing Message:
"Boost your daily movement, even when your work keeps you in a chair."

* Push marketing information to users when they are most likely to be on the app tracking their activity.  These key times are Monday and Tuesdays from 12-2PM and 5-7PM.

* Start User Challenges when they are most likely to be on the app tracking their activity.  These key times are Monday and Tuesdays from 12-2PM and 5-7PM.

* Because users are consistently wearing their devices throughout the entire day and night, There is an opportunity to market the app as Always-on wellness insights.  Highlight "all-day insights" in product messaging — not just workouts.

* Users had high engagement with sleep tracking features. This offers an opportunity for the app to be positioned as a sleep optimization coach and a holistic health tool, not just a passive tracker. This is also an opportunity to create smart sleep features (e.g., recovery suggestions, bedtime reminders).

* Because higher caloric expenditure is associated with more efficient sleep, Bellabeat can market around the idea that “More active days could contribute to better sleep quality.”


  



