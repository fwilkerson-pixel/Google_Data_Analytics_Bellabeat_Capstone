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


### Installing Packages & Loading Libraries
![image](https://github.com/user-attachments/assets/2cd98e45-ddc6-4a22-ade6-d83240199a90)

### Import CSV Files


### Data Examination
To obtain an initial overview of the dataset, the glimpse() and colnames() functions were used in RStudio to examine the structure of the data and identify available variables.




