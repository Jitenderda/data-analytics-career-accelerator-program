- # Python and Pandas Practice Notes

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
- `df.shape` returns values in this order:

```text
(rows, columns)

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
