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
