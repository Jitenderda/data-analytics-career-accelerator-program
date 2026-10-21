- # Python and Pandas Practice Notes
---
## Day 1 — Python and Pandas Basics

### Topics covered

- Imported the Pandas library using `import pandas as pd`
- Learned that `pd` is an alias for Pandas
- Created a Python dictionary containing vehicle data
- Learned about:
  - Dictionaries
  - Keys
  - Lists
  - Values
- Converted a dictionary into a Pandas DataFrame
- Learned that `df` is commonly used as the name of a DataFrame
- Checked the size of a DataFrame using `df.shape`
- Checked column names using `df.columns`
- Inspected DataFrame information using `df.info()`
- Reviewed numerical data using `df.describe()`
- Selected a column from a DataFrame
- Calculated:
  - Total revenue
  - Total units sold
  - Average revenue
  - Maximum revenue
- Sorted data by revenue
- Filtered rows based on a condition
- Created a calculated column for revenue per unit

### Day 1 business observation

All three vehicle models generated the same revenue per unit of 30,000. Therefore, the difference in total revenue was caused by the number of units sold rather than the revenue earned per unit.

### Important corrections

- A dictionary is not yet a DataFrame.
- A DataFrame is created using `pd.DataFrame(data)`.
- `df.shape` returns values in this order: `(rows, columns)`.
---
## Day 2 — Grouping Data with Pandas

### Topics covered

- Created a second dataset with repeated vehicle models and different regions.
- Converted the dictionary into a Pandas DataFrame.
- Learned why repeated categories are useful for grouping analysis.
- Grouped revenue by vehicle model.
- Calculated total units sold by vehicle model.
- Grouped revenue by region.
- Calculated total revenue for each region.
- Used grouped results to identify the highest- and lowest-performing regions.
- Converted numerical results into a business recommendation.

### Results

#### Total revenue by vehicle model

| Vehicle Model | Total Revenue |
|---|---:|
| A1 | 900,000 |
| B1 | 750,000 |
| C1 | 660,000 |

#### Total units sold by vehicle model

| Vehicle Model | Total Units Sold |
|---|---:|
| A1 | 30 |
| B1 | 25 |
| C1 | 22 |

#### Total revenue by region

| Region | Total Revenue |
|---|---:|
| Delhi | 660,000 |
| Gurugram | 450,000 |
| Noida | 960,000 |
| Sonipat | 240,000 |

### Day 2 business observation

Noida generated the highest revenue at 960,000, while Sonipat generated the lowest revenue at 240,000. The business should investigate the reasons for Sonipat’s lower performance, such as demand, dealer coverage, product availability, pricing, or promotional activity. Based on the findings, targeted promotional or dealer-support activities could be considered.

### Important learning

Grouping data helps compare performance across categories such as vehicle models and regions. However, a lower result does not immediately explain the reason for poor performance. Further analysis is needed before making a final business decision.

### Personal reflection

I learned how to group data and calculate totals using Pandas. I also practiced explaining numerical results in business language instead of only looking at the numbers.

---

## Day 3 — Sorting and Visualizing Data

### Topics covered

- Sorted grouped revenue results from highest to lowest.
- Learned that grouped results can initially appear as a Pandas Series.
- Used `reset_index()` to convert the index into a normal column.
- Created a clean DataFrame containing Region and Revenue.
- Introduced Matplotlib for data visualization.
- Created a bar chart using regional revenue.
- Added a chart title and axis labels.
- Converted revenue from rupees into lakhs for easier interpretation.
- Interpreted the bar chart using business language.

### Sorting result

The regional revenue was sorted in descending order:

| Region | Revenue |
|---|---:|
| Noida | 960,000 |
| Delhi | 660,000 |
| Gurugram | 450,000 |
| Sonipat | 240,000 |

### Revenue in lakhs

| Region | Revenue in Lakhs |
|---|---:|
| Noida | 9.6 |
| Delhi | 6.6 |
| Gurugram | 4.5 |
| Sonipat | 2.4 |

### Important learning

The chart initially showed scientific notation because the values were large and were measured in rupees. The revenue was divided by 100,000 to display it in lakhs, making the chart easier to understand.

For example:

- 960,000 rupees = 9.6 lakhs
- 660,000 rupees = 6.6 lakhs

### Day 3 business observation

Noida has the highest revenue, while Sonipat has the lowest revenue. The business should investigate the reasons for Sonipat’s lower sales, including product demand, product availability, dealer performance, pricing, and promotional activity. After identifying the main cause, the company can take targeted actions such as improving product availability, supporting dealers, or running suitable promotional campaigns in the region.

### Personal reflection

I learned how to sort grouped results and convert them into a clean DataFrame. I also created my first bar chart using Matplotlib and learned how to present large revenue values in lakhs for easier business interpretation.

---

## Day 4 — Data Cleaning and Missing Values

### Part 1 — Missing Values and Duplicate Records

- Learned what missing values are.
- Understood the difference between `None`, `NaN`, empty text, and `0`.
- Detected missing values using `isna()`.
- Filled a missing City value with `Unknown`.
- Filled a missing Salary value using the median.
- Detected duplicate records using `duplicated()`.
- Removed duplicate records using `drop_duplicates()`.
- Verified that the cleaned DataFrame has no missing or duplicate values.

### Part 2 — Data Types and Type Conversion

- Checked column data types using `dtypes`.
- Converted Salary from `float64` to `int64`.
- Added a new `Join_Date` column.
- Converted text dates using `pd.to_datetime()`.
- Learned that correct data types are important for accurate analysis.

### Day 4 Reflection

Today I learned how to clean a DataFrame before using it for analysis. I practiced finding missing values, replacing a missing city with `Unknown`, and filling a missing salary with the median.

I also learned how to identify and remove duplicate records. I checked data types, converted the Salary column to integer, added a new column, and converted text dates into proper date values.

This session helped me understand that data cleaning is an important step before analysis because missing values, duplicates, and incorrect data types can affect the accuracy of the results.

---

## Day 5 — Exploratory Data Analysis

### Topics covered

- Reviewed a cleaned DataFrame.
- Checked the number of rows and columns.
- Reviewed column names and data types.
- Confirmed that no missing values remained.
- Used `describe()` to summarize numerical and date columns.
- Compared average salary and median salary.
- Identified the highest and lowest salary.
- Extracted the year and month from a date column.
- Found the earliest and latest joining dates.
- Used `idxmax()` to find the row containing the highest salary.
- Used `.loc` to display selected values from that row.
- Converted analysis results into business observations.

### Data overview

- Rows: 5
- Columns: 5
- Year of records: 2023
- Date range: 15 January 2023 to 12 May 2023
- Missing values: 0

### Salary summary

- Average salary: 52,900
- Median salary: 52,500
- Highest salary: 65,000
- Lowest salary: 42,000
- Salary difference: 13,000

### Highest-paid employee

- Employee: Arjan
- Salary: 65,000

### Date-based observation

The data covers a five-month period from January to May 2023. Since all records belong to 2023, the dataset represents only part of one year. It is therefore limited for analyzing a complete annual trend. At least one full year of data would be more suitable for studying seasonal or yearly patterns.

### Day 5 Reflection

Today I learned how to explore a cleaned DataFrame using summary statistics and date analysis. I practiced comparing the average and median, finding the minimum and maximum values, and identifying the highest-paid employee using `idxmax()` and `.loc`.

I also learned how to extract the year and month from a date column and how to identify the earliest and latest dates. This helped me understand that exploratory data analysis is not only about calculating numbers; it also involves checking the time period and limitations of the data before making conclusions.

### Day 5 Test Result

Score: 12/16 — 75%

The test helped me understand the difference between exploratory data analysis, data cleaning, mean, median, percentiles, date ranges, and sample-size limitations. I also practiced identifying the row containing the highest salary using `idxmax()` and `.loc`.
