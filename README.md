# Cyclistic Bike-Share Analysis

## Project Overview

**Technologies:**
- Data Visualization: PowerBI
- Domain: Data Analysis and Data Visualization

## Introduction

In this case study, as a Business analyst at Cyclistic, a bike-share company in Chicago, your role is to analyze and identify trends in Cyclistic's historical trip data. The goal is to understand how casual riders and annual members use Cyclistic bikes differently. Your insights will inform the development of a new marketing strategy to convert casual riders into annual members, backed by compelling data insights and professional data visualizations.

## Scenario

You are part of the marketing analyst team at Cyclistic, focusing on maximizing annual memberships. Your team aims to design a new marketing strategy based on understanding the differences in bike usage between casual riders and annual members.

## Key Tasks in the Preparation Phase

1. **Download Data:**
- Downloaded the previous 12 months of Cyclistic trip data from the Sources.

2. **Data Organization:**
- identified how the data is organized.
- Sorted and filter the data for better understanding.

## Key Tasks in the Processing Phase

1. **Data Check:**
- The dataset has been thoroughly inspected for errors, inconsistencies, or missing values. This initial data check is crucial to ensure the quality and reliability of the data used for analysis.
  
2. **Tool Selection:**
- The appropriate tools for analysis have been chosen based on the nature of the data and the analysis requirements. In this case, tools such as PowerBI have been selected for their effectiveness in creating compelling visualizations and gaining insights from the data.

3. **Data Transformation:**
- The data has undergone necessary transformations to make it suitable for analysis. This includes tasks such as organizing, aggregating, and formatting the data to facilitate effective analysis. Transformations are performed to ensure that the data is in a usable format for the selected tools.

4. **Documentation:**
- The cleaning process has been thoroughly documented to maintain transparency and allow for a clear understanding of the steps taken. Details such as the specific transformations applied, any data cleaning activities performed, and the rationale behind these actions are documented for reference and reproducibility. 

## Key Tasks in the Analysis Phase

1. **Data Aggregation:**
- The data has been aggregated to enhance its usefulness and accessibility. This involves consolidating information to provide a more concise and manageable dataset. Aggregation allows for a higher-level view of the data, facilitating analysis and interpretation.

2. **Organize and Format:**
- The data has been organized and formatted systematically to ensure clarity and ease of interpretation. This step involves structuring the data in a logical manner, defining relationships between different variables, and formatting it in a way that is conducive to analysis.

3. **Perform Calculations:**
- Relevant calculations have been conducted on the data to derive meaningful insights. This may include computations such as averages, percentages, or other mathematical operations to extract valuable information and metrics from the dataset.

4. **Identify Trends:**
- The data has been thoroughly analyzed to identify trends and relationships. This involves examining patterns, correlations, and anomalies within the dataset. The identification of trends provides valuable insights into the underlying dynamics of the data, helping in the formulation of actionable recommendations.

5. **DAX and Measure created:**

- created Data Analysis Expressions (DAX) formulas in Power BI for custom calculations.
- Defined measures for key performance indicators (KPIs) using DAX in Power BI.

**For the Busiest Day in week**
```
MostFrequentDayName = 
VAR DayNameCounts =
    SUMMARIZE(
        'data analytics (2) (1)',
        'data analytics (2) (1)'[Day Name],
        "DayNameCount", COUNTROWS('data analytics (2) (1)')
    )
VAR MaxCount =
    MAXX(DayNameCounts, [DayNameCount])
RETURN
    MAXX(
        FILTER(DayNameCounts, [DayNameCount] = MaxCount),
        [Day Name]
    )
```
**For the Busiest Timeslot in day**

```
MostFrequentTimeCategory = 
VAR TimeCounts =
    SUMMARIZE(
        'data analytics (2) (1)',
        'data analytics (2) (1)'[started_at],
        "TimeCount", COUNTROWS('data analytics (2) (1)')
    )
VAR MaxCount =
    MAXX(TimeCounts, [TimeCount])
VAR MostFrequentTime =
    MAXX(
        FILTER(TimeCounts, [TimeCount] = MaxCount),
        [started_at]
    )
RETURN
    SWITCH(
        TRUE(),
        HOUR(MostFrequentTime) >= 8 && HOUR(MostFrequentTime) < 12, "Morning",
        HOUR(MostFrequentTime) >= 12 && HOUR(MostFrequentTime) < 18, "Afternoon",
        HOUR(MostFrequentTime) >= 18 && HOUR(MostFrequentTime) < 20, "Evening",
        "Other"
    )
```

## Key Tasks in the Sharing Phase

1. **Choose Visualization Tool:**
- Select The appropriate tools for analysis have been chosen based on the nature of the data and the analysis requirements. In this case, tools such as PowerBI have been selected for their effectiveness in creating compelling visualizations and gaining insights from the data.eau for creating compelling data visualizations.

2. **Create Visualizations:**
- Created visuals showcasing differences in bike usage between casual riders and annual members.

3. **Ensure Clarity:**
- Used artistic principles for contrast, size, color, and shape to draw attention.
- Added clear elements like headlines, subtitles, and labels for meaning.

4. **Refinement:**
- Special attention has been given to detail during the refinement process of the visualizations. This step involves fine-tuning the visual elements to enhance clarity, coherence, and overall visual appeal. Refining the visualizations contributes to a more impactful presentation of the data insights.

## Project Snapshots

- **Cyclist Bike Share Analysis Dashboard**

![main dashboard](https://github.com/Shubham301099/Cyclist-Bike-Share-Analysis-/assets/154081009/1c0373a9-71aa-4e5d-ac00-486cbf702c34)


- **Project's summary and recommendations**

![summary and recommendations](https://github.com/Shubham301099/Cyclist-Bike-Share-Analysis-/assets/154081009/f48a02ee-ee83-4e75-95dc-1f2f243b87b2)


## Approach

1. **Analyze Rider Data:**
 - Collect and analyze data on the frequency, duration, and types of rides by Cyclistic bike users.

2. **Segment Riders:**
- Segment riders into casual and annual members based on behavior, membership type, and usage patterns.

3. **Create Data Visualizations:**
- Develop visuals for the number of rides per day, week, and month, along with total trip duration per week.

4. **Get Insights:**
- Upload visualizations to PowerBI and create a report or presentation highlighting key findings.



## Results

### Deliverables:

1. **Business Task Statement:**
- The primary goal is to understand how casual riders and annual members use Cyclistic bikes differently. This understanding will inform the development of a new marketing strategy to convert casual riders into annual members.

2. **Data Sources Description:**
- The data for this analysis is sourced from Cyclistic's historical trip data, covering the previous 12 months. The dataset includes information on bike rides, customer types, and usage patterns.

3. **Data Cleaning Documentation:**
- The data has been checked for errors during the initial inspection. Any inconsistencies or errors found during this phase were addressed to ensure the reliability of the analysis. Details of the cleaning process have been documented for transparency.

4. **Analysis Summary:**
 - The analysis involved aggregating, organizing, and formatting the data for effective use. Key trends and relationships were identified through calculations, allowing for insights into how different customer types use Cyclistic bikes. The analysis focuses on answering the business task by providing actionable findings.

5. **Supporting Visualizations:**
- Visualizations have been created using PowerBI to highlight differences in bike usage between casual riders and annual members. These visuals include graphs showcasing the number of rides per day, week, and month, along with total trip duration per week. The aim is to present insights in a clear and compelling manner.

6. **Top Three Recommendations:**
- Introduce targeted promotions to encourage casual riders to become annual members.
- Optimize bike availability and locations based on high-traffic areas identified in the analysis.
- Enhance the user experience for casual riders through incentives, such as discounts on annual memberships after a certain number of rides.
---


