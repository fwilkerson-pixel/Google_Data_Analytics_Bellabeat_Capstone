# Bellabeat Capstone Case Study

##### Author: F. Wilkerson
##### Date: 02/20/2025

## Introduction
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
The goal of this project is to identify current trends in smart health device usage.  This information will be used to give high-level recommendations for how these trends can inform Bellabeat marketing strategy going forward for one Bellabeat product. 
<br/><br/>

## Stakeholders
**Primary Stakeholders:** 
  * Urška Sršen: Bellabeat co-founder and Chief Creative Officer
  * Sando Mur: Bellabeat co-founder

**Secondary Stakeholders:** 
 * Bellabeat marketing analytics team
 <br/><br/>
 
## Data Overview

### Data Source
The dataset used in this analysis is publicly available [FitBit Fitness Tracker data](https://www.kaggle.com/datasets/arashnic/fitbit), shared by Mobius on Kaggle. It contains anonymized user information, including daily physical activity, sleep patterns, and heart rate data.  The original dataset was created by Furberg, Robert; Brinton, Julia; Keating, Michael; and Ortiz, Alexa, and is available on Zenodo:  [https://zenodo.org/record/53894#.YMoUpnVKiP9](https://zenodo.org/record/53894#.YMoUpnVKiP9)

The data was collected through a distributed survey conducted via Amazon Mechanical Turk between 03.12.2016-05.12.2016. A total of thirty eligible Fitbit users voluntarily consented to share their personal tracker data for the purposes of this study.

### Data Limitations
While the dataset provides valuable insights into user behavior with Fitbit smart devices, there are several important limitations to consider:

**Source and Collection Method:**
The data was self-reported by participants recruited via Amazon Mechanical Turk (MTurk). This platform tends to attract a specific demographic—typically younger, more tech-savvy individuals—which may introduce selection bias. Additionally, responses were collected over a short time frame (December 3–5, 2016), providing only a limited snapshot of user activity.

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

## Process Data

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
<br/>

Sample...<br/><br/>

<ins>***daily_activity***</ins>
![image](https://github.com/user-attachments/assets/d69b1df2-ed31-40e1-b96f-e419132bc2da)

<ins>***sleep_day***</ins>
![image](https://github.com/user-attachments/assets/6e543740-73f0-4cb7-a01a-ab152bd47628)

<ins>***hourly_intensity***</ins>
![image](https://github.com/user-attachments/assets/2add441f-ab58-4a55-86ff-02d02e2ef0e8)


