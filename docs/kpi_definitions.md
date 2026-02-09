# KPI Definitions & DAX Measures

## Overview
This document defines the key KPIs and base DAX measures used in the Healthcare Analytics Excel Dashboard.  
All measures are created using **Excel Power Pivot (Calculation Area)** and are reused across PivotTables and dashboard visuals to ensure consistency.

---

## Measure Creation Method (Excel Power Pivot)

Since this project is built using **Excel (not Power BI)**, DAX measures are created in the **Calculation Area** of Power Pivot.

- Excel Power Pivot does not provide a separate “New Measure” ribbon like Power BI
- The Calculation Area is the recommended and standard approach
- Measures act as centralized business logic for reporting

---

## Base Measures

### Total Visits
**Definition:** Counts the total number of patient visits.

Total Visits :=
COUNT(Fact_Visits[Visit ID])

### Total Patients
**Definition:** Counts unique patients who have at least one visit.

Total Patients :=
DISTINCTCOUNT(Fact_Visits[Patient ID])

### Total Treatments
**Definition:** Counts all treatments administered during visits.

Total Treatments :=
COUNT(Fact_Treatments[Treatment ID])

### Total Lab Tests
**Definition:** Counts all lab tests conducted for patient visits.

Total Lab Tests :=
COUNT(Fact_LabResults[Lab Result ID])

### Average Visits per Patient
**Definition:** Calculates the average number of visits per patient.

Avg Visits per Patient :=
DIVIDE([Total Visits], [Total Patients])

**Note on Abnormal Lab Results Logic**

The `Is_Abnormal` column is stored as a numeric flag:
- 1 = Abnormal
- 0 = Normal
- Blank = Pending / Not Available

Therefore, DAX measures compare the column to `1` instead of using `TRUE()`,
ensuring compatibility with Excel Power Pivot data types.

## Advanced KPI Measures

Advanced KPIs were created using DAX in the Excel Power Pivot Calculation Area.
These KPIs provide operational, clinical, and executive-level insights.

### Abnormal Lab Results
Counts lab tests flagged as abnormal.

### Abnormal Lab Result Percentage
Measures the proportion of abnormal lab results against total tests.

### Cancelled Visits
Tracks visits that were cancelled to monitor operational inefficiencies.

### Completed Visits
Counts successfully completed patient visits.

### Visit Completion Rate
Indicates the percentage of visits completed successfully.

### Treatments per Visit
Measures treatment intensity per patient visit.

### Year-over-Year Visit Growth
Evaluates visit trends compared to the previous year using the Dim_Date table.

