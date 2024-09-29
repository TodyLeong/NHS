# NHS Diagnostic Analysis Using Python

## Overview
This project is part of a group assignment for the **Data Analytics course at the London School of Economics (LSE)**, where I served as the project leader. The aim of this analysis is to evaluate the sufficiency of staffing and capacity within NHS networks, as well as to assess the actual utilisation of resources. Using both internal data on service utilisation and appointment details, and external data from sources such as Twitter (X), we aim to provide insights that will inform strategic planning and resource optimisation for the NHS.

## Business Background and Key Questions
The **National Health Service (NHS)**, England's publicly funded healthcare system, faces challenges in resource allocation due to increasing population growth. This analysis aims to address these challenges by focusing on the following key areas:

- **Staffing and Capacity Evaluation**: Determine whether current staffing levels and healthcare capacity are sufficient to meet patient demand.
- **Actual Resource Utilisation**: Analyse the actual utilisation of resources, including service appointments, to identify inefficiencies and suggest improvements.
- **Service Demand and Patterns**: Understand the demand for different types of services, both by time and type, to support effective planning.
- **External Sentiment Analysis**: Leverage data from Twitter to understand public sentiment and feedback regarding NHS services.

## Data Cleaning and Preparation
### Steps Taken:
1. **Initial Data Exploration**
   - The four datasets (`actual_duration`, `national_categories`, `appointments_regional`, and `tweets`) were imported into Python.
   - Used descriptive statistics and metadata (`file_data.info()` and `file_data.describe()`) to conduct a sense-check, ensuring accuracy, consistency, and reliability of data.

2. **Handling Duplicates**
   - Investigated and removed duplicates across the datasets:
     - **`actual_duration` dataset**: Found and removed 21,604 duplicate records.
     - No duplicates were found in the remaining datasets, ensuring quality and reliability.

3. **Data Merging and Integration**
   - Merged datasets using an outer join to retain all rows, ensuring that no data was excluded. This allowed us to retain comprehensive information, even if there were unmatched entries between datasets.

4. **Outlier and Irrelevant Data Removal**
   - Removed irrelevant data and filtered outliers to ensure the integrity of the analysis and produce clear data visualisations.

## Data Analysis Approach
### Tools and Libraries
This analysis was conducted using **Python**.

#### Libraries Used
- **Pandas (`import pandas as pd`)**: 
  - For data manipulation, including grouping, aggregating, and merging.
  
- **NumPy (`import numpy as np`)**: 
  - For numerical operations and data normalisation.

- **Matplotlib (`import matplotlib.pyplot as plt`)**: 
  - For visualisations, such as bar charts, line graphs, and histograms.

- **Seaborn (`import seaborn as sns`)**: 
  - For statistical graphics, including heatmaps and pair plots.

- **Statsmodels (`import statsmodels.api as sm`, `import statsmodels.stats.api as sms`)**: 
  - For statistical modelling and hypothesis testing.

## Key Insights and Visualisation Summary

### Patterns, Trends, and Insights
1. **Appointments by Region**:
   - The dataset initially contained 106 locations. The **NHS North-West London ICB** recorded the highest number of appointments at 12,142,390, followed by **NHS North-East London ICB** with 9,558,891 appointments.
   - Three of the top five locations with the highest number of appointments are situated in London, highlighting a regional concentration of healthcare demand (Figure 1).

   ![Top Five Locations with the Highest Number of Appointments](figure_1.png)

2. **National Categories Analysis**:
   - **General Consultation Routine** had the highest number of appointments, followed by **General Consultation Acute** (Figure 2).
   - On the other hand, **Group Consultation** and **Group Education** had the lowest number of appointments, indicating potentially less demand or lower accessibility for these services (Figure 3).

   ![Highest Number of Appointments for National Categories](figure_2.png)
   ![Lowest Number of Appointments for National Categories](figure_3.png)

3. **Seasonal Trends in Appointments**:
   - The data showed that **November 2021** recorded the highest number of appointments, followed by **October 2021** and **March 2022**. Notably, three of the top four months with the highest number of appointments fell in the autumn season (September to November).
   
   | Rank | Month          | No of Appointments  |
   |------|----------------|---------------------|
   | 1    | November 2021  | 30,405,070          |
   | 2    | October 2021   | 30,303,834          |
   | 3    | March 2022     | 29,595,038          |
   | 4    | September 2021 | 28,522,501          |

   - **General Practice** accounted for the overwhelming majority of appointments, with a total of 270,811,691, while other service settings such as **Primary Care Network** and **Extended Access Provision** had significantly lower numbers (Figure 5).

   ![Appointments Number for Service Settings Over Time](figure_5.png)

4. **Service Setting and Seasonal Influence**:
   - A clear trend was observed where appointments in **General Practice** increased steadily from August, peaking in **November** and then again in **March**. Similar trends were seen for **Care-Related Encounters**, indicating a seasonal influence on service utilisation (Figures 6 and 7).

   ![Appointments Number for Service Setting across Seasons](figure_6.png)
   ![Appointments Number for Context Types Over Time](figure_7.png)

## Patterns and Predictions

### Key Findings on Resource Utilisation
1. **Correlation Between Appointment Time and Booking**:
   - A negative correlation was observed between the number of appointments and the time from booking to appointment (Figure 9). This trend suggests inefficiencies, particularly when appointments are scheduled at short notice, which impacts resource allocation.

   ![Trends Between Time from Booking to Appointment Over Time](figure_9.png)

2. **Appointment Mode Utilisation**:
   - The most used appointment modes were **Face-to-Face** and **Telephone**, with a smaller proportion allocated to **Home Visits** and **Online Appointments** (Figure 10). This suggests that resource allocation should focus on prioritising these primary modes of service delivery.

   ![Trends for Different Appointment Modes](figure_10.png)

3. **Missed Appointments (Did Not Attend - DNAs)**:
   - Approximately **4.55%** of patients (equivalent to **54,600** patients) did not attend their appointments (Figure 11). This represents a significant impact, leading to wasted resources and reducing accessibility for other patients. Immediate strategies are needed to address this issue effectively.

   ![Distribution of Appointment Status](figure_11.png)

### Findings on Staffing and Capacity
1. **Staff Utilisation**:
   - The daily appointment rates were below the NHS's recommended maximum capacity of **1,200,000** per day, suggesting that current staffing levels are sufficient to meet existing demand (Figure 12).

   ![Monthly Capacity Utilisation](figure_12.png)

2. **Distribution of Healthcare Professionals**:
   - A well-balanced distribution of healthcare professionals was observed across networks (Figure 13). This ensures comprehensive coverage for patients; however, further examination may be required in specific roles to optimise care delivery.

   ![Distribution of Healthcare Professional Type](figure_13.png)

## Recommendations
1. **Enhance Twitter Data Analysis**:
   - The lack of a time frame in the Twitter dataset limited our ability to perform deeper analysis. Adding a time frame could significantly improve the potential for robust sentiment analysis and trend evaluation.

2. **Reduce Missed Appointments**:
   - Implement targeted strategies, such as reminders and follow-ups, to reduce missed appointments and maximise resource utilisation.

3. **Prioritise Face-to-Face and Telephone Modes**:
   - Given the high utilisation of **Face-to-Face** and **Telephone** appointments, these modes should be prioritised in resource allocation and planning.

4. **Seasonal Demand Planning**:
   - The seasonal trends indicate a higher demand for appointments in autumn and early spring. Resource allocation should consider these peaks to ensure sufficient staffing and availability during these periods.
