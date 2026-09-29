# Airline Passenger Satisfaction Analysis

## Table of Contents

1. [Problem Statement](#problem-statement)
2. [Executive Summary](#executive-summary)
3. [Project Structure](#project-structure)
4. [Data and Data Dictionary](#data-and-data-dictionary)
5. [Analytical Objectives](#analytical-objectives)
6. [Key Findings](#key-findings)
7. [Conclusions and Recommendations](#conclusions-and-recommendations)
9. [Sources](#sources)

---

## Problem Statement

Passenger satisfaction is an important indicator of airline customer experience, but overall satisfaction figures do not explain which passengers are most dissatisfied or which aspects of their journey are associated with dissatisfaction. This project analyzes passenger demographics, travel characteristics, service ratings, and operational delays to identify patterns associated with passenger satisfaction and dissatisfaction.

---

## Executive Summary

This project analyzes an Airline Passenger Satisfaction dataset containing **129,880 passenger records and 25 variables**. The dataset includes demographic information, travel characteristics, ratings for 14 passenger services, departure and arrival delays, and an overall passenger satisfaction outcome. The analysis focuses on exploratory data analysis (EDA), using descriptive statistics, group comparisons, correlation analysis, and visualizations to investigate patterns in passenger satisfaction.

The analysis found that approximately **56.5% of passengers were neutral or dissatisfied**. Dissatisfaction was not evenly distributed across passenger groups. Economy passengers showed substantially higher dissatisfaction than Business passengers, while Adults and Young Adults represented approximately **70% of dissatisfied passengers**. Among dissatisfied Young Adults and Adults, **inflight Wi-Fi and ease of online booking** were among the lowest-rated service areas.

Operational factors also showed an important relationship with satisfaction. Approximately **53% of passengers with no arrival delay were neutral or dissatisfied**, compared with approximately **64% among passengers experiencing delays of more than 15 minutes**. Flight distance also differed between satisfaction groups; however, this relationship needs to be interpreted alongside travel class because Business passengers had substantially longer average flight distances than Economy and Economy Plus passengers.

Overall, the findings suggest that passenger dissatisfaction is associated with a combination of **passenger segment, service experience, and operational performance**. The analysis highlights digital services, the Economy/Economy Plus passenger experience, and delay management as areas that could be investigated further by the airline.

---

## Data and Data Dictionary

### Data Source

The dataset used in this project is the **Airline Passenger Satisfaction** dataset available on Kaggle.

Source:

https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction

The original dataset contains **129,880 observations and 25 columns**. The dataset was used to investigate passenger satisfaction through demographic, travel, service, and operational variables.

### Data Cleaning

The following preprocessing steps were performed:

* Removed identifier columns that were not useful for analysis.
* Investigated missing values.
* Identified **393 missing values** in `Arrival Delay in Minutes`.
* Created an `Age Groups` feature to allow comparison of satisfaction across age segments.
* Created a `satisfaction_numeric` feature where:

  * `0` = Neutral or dissatisfied
  * `1` = Satisfied
* Created `Arrival Delay Group` categories to analyze the relationship between delay length and satisfaction.

### Data Dictionary

| Feature                             | Description                                  | Type           |
| ----------------------------------- | -------------------------------------------- | -------------- |
| `Gender`                            | Passenger gender                             | Categorical    |
| `Customer Type`                     | Type of customer                             | Categorical    |
| `Age`                               | Passenger age                                | Numerical      |
| `Age Groups`                        | Engineered passenger age category            | Categorical    |
| `Type of Travel`                    | Purpose/type of passenger travel             | Categorical    |
| `Class`                             | Travel class                                 | Categorical    |
| `Flight Distance`                   | Distance travelled by passenger              | Numerical      |
| `Inflight wifi service`             | Passenger rating of inflight Wi-Fi           | Numerical, 1–5 |
| `Departure/Arrival time convenient` | Rating of departure/arrival time convenience | Numerical, 1–5 |
| `Ease of Online booking`            | Rating of online booking experience          | Numerical, 1–5 |
| `Gate location`                     | Rating of gate location                      | Numerical, 1–5 |
| `Food and drink`                    | Rating of food and drink                     | Numerical, 1–5 |
| `Online boarding`                   | Rating of online boarding                    | Numerical, 1–5 |
| `Seat comfort`                      | Rating of seat comfort                       | Numerical, 1–5 |
| `Inflight entertainment`            | Rating of inflight entertainment             | Numerical, 1–5 |
| `On-board service`                  | Rating of onboard service                    | Numerical, 1–5 |
| `Leg room service`                  | Rating of leg room                           | Numerical, 1–5 |
| `Baggage handling`                  | Rating of baggage handling                   | Numerical, 1–5 |
| `Checkin service`                   | Rating of check-in service                   | Numerical, 1–5 |
| `Inflight service`                  | Rating of inflight service                   | Numerical, 1–5 |
| `Cleanliness`                       | Rating of cleanliness                        | Numerical, 1–5 |
| `Departure Delay in Minutes`        | Departure delay duration                     | Numerical      |
| `Arrival Delay in Minutes`          | Arrival delay duration                       | Numerical      |
| `satisfaction`                      | Overall passenger satisfaction               | Categorical    |
| `satisfaction_numeric`              | Encoded satisfaction outcome                 | Binary         |
| `Arrival Delay Group`               | Engineered arrival-delay category            | Categorical    |

> **Note:** `id` and `Unnamed: 0` are identifier/index columns and are not used as analytical features in the cleaned dataset.

---

## Analytical Objectives

The analysis was structured around the following objectives:

### 1. Passenger Profiling

Understand the demographic and travel characteristics of passengers in the dataset.

### 2. Assess Overall Satisfaction

Measure the overall proportion of satisfied and neutral/dissatisfied passengers.

### 3. Identify Dissatisfied Passenger Segments

Determine which passenger groups show higher levels of dissatisfaction based on characteristics such as age and travel class.

### 4. Examine Service Experience

Identify which passenger service ratings have stronger associations with overall satisfaction.

### 5. Investigate Dissatisfied Passenger Experience

Examine the lowest-rated services among dissatisfied Young Adult and Adult passengers.

### 6. Examine Operational Delays

Assess whether arrival delays are associated with passenger dissatisfaction.


## Key Findings

### Overall Satisfaction

Approximately **56.5% of passengers were neutral or dissatisfied**, indicating that dissatisfaction represents a substantial portion of the passenger population.

### Passenger Segments

Dissatisfaction varies across travel classes. Economy passengers show substantially higher dissatisfaction than Business passengers.

Age also shows differences in dissatisfaction, with **Young Adults and Adults** showing higher dissatisfaction than some other age groups.

### Service Experience

Correlation analysis was used to examine the relationship between individual service ratings and overall satisfaction.

Because service ratings range from 1–5 while satisfaction was represented as a binary 0/1 variable, the resulting correlations indicate **association rather than causation**.

### Dissatisfied Young Adults and Adults

Among neutral/dissatisfied passengers:

* **Inflight Wi-Fi** is among the lowest-rated services for both Young Adults and Adults.
* **Ease of Online Booking** is also among the lowest-rated services for both groups.
* **Online Boarding** is particularly low among dissatisfied Young Adults.

These findings highlight digital and online aspects of the passenger journey as areas for further investigation.

### Overall delays

delays show a relationship with dissatisfaction.

Approximately:

* **52.6%** of passengers with no delay were neutral/dissatisfied.
* **58.8%** with a 1–15 minute delay were neutral/dissatisfied.
* **64.3%** with a 16–30 minute delay were neutral/dissatisfied.
* **63.9%** with a 31–60 minute delay were neutral/dissatisfied.
* **64.4%** with a delay exceeding 60 minutes were neutral/dissatisfied.

This suggests that dissatisfaction increases notably once delays exceed approximately 15 minutes.
---

## Conclusions and Recommendations

The analysis indicates that passenger dissatisfaction is associated with several passenger, service, and operational characteristics.

### 1. Investigate the Digital Passenger Experience

Inflight Wi-Fi, online booking, and online boarding are among the lower-rated service areas for dissatisfied younger passenger groups.

The airline should investigate the quality and reliability of its digital services, particularly for younger passengers.

### 2. Investigate the Economy Passenger Experience

Economy and Economy Plus passengers show higher dissatisfaction than Business passengers.

Further analysis should identify which specific aspects of the Economy experience contribute to this difference, including service quality, comfort, entertainment, and digital services.

### 3. Focus on Delays Above 15 Minutes

The analysis shows a noticeable increase in dissatisfaction once arrival delays exceed 15 minutes.

The airline could investigate proactive communication, passenger support, and delay-management strategies for passengers experiencing longer delays.

### 4. Use Passenger Segmentation

The findings suggest that different passenger groups may have different pain points.

Instead of treating all passengers as one group, the airline could use passenger segments such as age group and travel class to identify and prioritize different areas for improvement.

---


## Sources

### Dataset

Teejmahal20. *Airline Passenger Satisfaction*. Kaggle.

https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction

### Python Libraries

* Pandas — data manipulation and analysis
* NumPy — numerical computing
* Matplotlib — data visualization
* Seaborn — statistical data visualization

---

## Important Visualizations

The following visualizations highlight the main findings of the analysis:

### 1. Overall Passenger Satisfaction

Shows the proportion of passengers who are satisfied versus neutral/dissatisfied.

### 2. Dissatisfaction by Travel Class

Highlights the substantially higher dissatisfaction observed among Economy passengers compared with Business passengers.

### 3. Dissatisfaction by Age Group

Shows the percentage of passengers within each age group who are neutral/dissatisfied.

### 4. Service Ratings and Satisfaction Correlation

Shows the association between the 14 passenger service ratings and overall satisfaction.

### 5. Service Ratings Among Dissatisfied Young Adults and Adults

Highlights the services receiving the lowest average ratings among the key dissatisfied passenger groups.

### 6. Arrival Delay and Satisfaction

Shows the increase in dissatisfaction across different arrival-delay categories.

---

## Project Limitations

Several limitations should be considered when interpreting the findings:

* The analysis identifies **associations rather than causation**.
* The dataset represents recorded passenger experiences and may not capture every factor affecting satisfaction.

---

## Author

**Sara**

Airline Passenger Satisfaction — Exploratory Data Analysis Project
