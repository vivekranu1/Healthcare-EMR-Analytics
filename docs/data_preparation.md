## Data Preparation

### Power Query Transformations
- Removed duplicates
- Standardized text fields
- Converted date columns
- Ensured consistent ID formats

### Derived Columns

#### YearMonthKey
Created to enable month-level aggregation and time-series analysis.
Used for trend analysis and year-over-year comparison.

#### Is_Abnormal
Created from Test Result column to convert clinical outcomes into a numeric flag.
- 1 = Abnormal
- 0 = Normal
- null = Pending

This enables aggregation, percentage calculation, and trend analysis of abnormal lab results.

#### Derived Date Dimension (Dim_Date)
Created from the Visit Date column of the Fact_Visits table to enable consistent time-based analysis.

The Date dimension includes attributes such as Year, Month, Month Name, and YearMonthKey, and is used to support trend analysis, month-level aggregation, and year-over-year (YoY) comparisons across all dashboards.

