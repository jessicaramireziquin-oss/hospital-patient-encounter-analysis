# Hospital Patient & Encounter Analysis

SQL + Tableau analysis of the **Hospital Patient Records** dataset from **Maven Analytics**, exploring patient encounters, costs, coverage, and readmission behavior.

## Overview

This project uses SQL to answer a set of business questions around hospital encounters, then visualizes key findings in an interactive Tableau dashboard. The goal was to practice translating real-world healthcare questions into SQL queries and surfacing patterns that would matter to hospital administrators or analysts, things like utilization trends, cost drivers, and readmission risk.

## Tools Used
- **SQL** — data querying and analysis
- **Tableau** — dashboard and data visualization

## Data Source
[Hospital Patient Records](https://www.mavenanalytics.io/) dataset, sourced from Maven Analytics.

## Objectives & Key Questions

### Objective 1: Encounters Overview
- How many total encounters occurred each year?
- For each year, what percentage of all encounters belonged to each encounter class (ambulatory, outpatient, wellness, urgent care, emergency, inpatient)?
- What percentage of encounters were over 24 hours versus under 24 hours?

### Objective 2: Cost & Coverage Insights
- How many encounters had zero payer coverage, and what percentage of total encounters does this represent?
- What are the top 10 most frequent procedures performed, and the average base cost for each?
- What are the top 10 procedures with the highest average base cost, and how many times were they performed?
- What is the average total claim cost for encounters, broken down by payer?

### Objective 3: Patient Behavior Analysis
- How many unique patients were admitted each quarter over time?
- How many patients were readmitted within 30 days of a previous encounter?
- Which patients had the most readmissions?

## Key Findings
- Encounter volume peaked in 2014 with 3,885 encounters, then declined before rising again in 2020–2021. 2022 shows only 220 recorded encounters, suggesting the year's data may be incomplete.
- Ambulatory encounters were the dominant class in most years, peaking at 60.26% in 2014, but their share declined to 36.91% by 2021. Outpatient encounters grew over the same period, reaching 40.17% in 2021 and overtaking ambulatory as the largest encounter class that year. Emergency and inpatient encounters remained comparatively small shares throughout.
- 13,586 encounters (48.71% of all 27,891 encounters) had zero payer coverage, nearly half of all encounters went unpaid by any payer.
- "Assessment of health and social care needs" was the most frequently performed procedure (4,596 occurrences), followed by hospice care (4,098). Most top-10 procedures shared an average base cost of $431. The most common base cost in the dataset. While renal dialysis stood out with a notably higher average cost of roughly $1,004.
- Admit to ICU had the highest average base cost of any procedure at $206,260.40, though it was performed only 5 times. Electrical cardioversion was far more common (1,383 occurrences) with an average base cost of $25,903.11. Showing that the highest-cost procedures aren't necessarily the ones driving the most total spend.
- Medicaid had the highest average total claim cost at roughly $6,205, followed by patients with no insurance at roughly $5,593. Dual Eligible patients had the lowest average claim cost at roughly $1,696.
- Unique patient volume rose from 2011 through the early years of the dataset, with notable spikes in 2014 Q1 (394 patients) and 2021 Q1–Q2 (417 and 414 patients). Volume was relatively stable from 2015–2020, generally ranging between ~225 and 260 unique patients per quarter. 2022 again appears incomplete, with only 103 unique patients recorded in Q1.
- 772 unique patients had a subsequent encounter within 30 days of a previous one, indicating a measurable level of short-term readmission across the dataset.
- Kimberly Collier had the highest number of 30-day readmissions (1,376), followed by Mariano O'Kon (876) and Shani Parisian (871).

## Dashboard
View the interactive dashboard on Tableau Public: [Hospital Patient Encounter Analysis Dashboard](https://public.tableau.com/views/HospitalPatientEncounterAnalysisDescriptiveAnalysis/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)


<img width="1317" height="1726" alt="dashboard-screenshot png " src="https://github.com/user-attachments/assets/2a40365d-42a5-40c3-9b80-201ed56ae2a5" />


## Files in This Repo
- `HOSPITAL_ANALYTIC_QUESTIONS_ANSWERS.sql` — SQL scripts used for the analysis
- `README.md` — project overview (this file)

## What I'd Improve Next
- Investigate the 2022 data gap further, confirm whether the dataset was simply cut off mid-year, or compare against a full quarter to verify the drop is a data limitation rather than a real trend.
- Explore the shift from ambulatory to outpatient encounters more closely, check whether it lines up with broader post-2020 healthcare trends, or whether specific procedures moved between the two classes over time.
