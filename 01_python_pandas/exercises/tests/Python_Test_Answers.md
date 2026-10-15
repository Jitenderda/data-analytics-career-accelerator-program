# Python and Pandas Test Answers

## Day 1 Answers

### Answer 1

The line:

```python
import pandas as pd
```

imports the Pandas library and gives it the short alias `pd`, so Pandas functions can be used by writing `pd`.

### Answer 2

`data` stores the information in a dictionary.

- Curly brackets `{}` contain the dictionary.
- The column names are dictionary keys.
- Square brackets `[]` contain lists of values.
- Values in the same position form one row.

This code creates a dictionary, not yet a DataFrame.

### Answer 3

The line:

```python
df = pd.DataFrame(data)
```

converts the dictionary called `data` into a Pandas DataFrame.

`df` represents the DataFrame and is the name assigned to the table.

### Answer 4

For a DataFrame with 5 rows and 4 columns:

```python
df.shape
```

returns:

```text
(5, 4)
```

The order is:

```text
(rows, columns)
```

Therefore:

- `5` represents the number of rows.
- `4` represents the number of columns.

### Answer 5

`df.info()` provides a technical summary of the DataFrame, including:

- Number of rows
- Number of columns
- Column names
- Non-null values
- Data types
- Memory usage

### Answer 6

```python
df["Revenue"].sum()
```

This selects the Revenue column and adds all its values.

### Answer 7

```python
df["Revenue"].mean()
```

calculates the arithmetic average of the Revenue column.

```python
df["Revenue"].max()
```

finds the largest value in the Revenue column.

### Answer 8

```python
df["Revenue"] > 300000
```

creates a Boolean Series containing `True` or `False` for each row.

The outer:

```python
df[...]
```

displays only the complete rows where the condition is `True`.

### Day 1 Result

Score: 12/15 — 80%

---

## Day 2 Answers

### Answer 1

```python
df2.groupby("Vehicle Model")["Revenue"].sum()
```

- `groupby("Vehicle Model")` groups the records according to vehicle model.
- `["Revenue"]` selects the Revenue column.
- `.sum()` adds the revenue values for each vehicle model.

### Answer 2

```python
df2.groupby("Vehicle Model")["UnitSold"].sum()
```

groups the data by vehicle model and calculates the total units sold for each model.

Expected results:

- A1: 30 units
- B1: 25 units
- C1: 22 units

### Answer 3

```python
df2.groupby("Region")["Revenue"].sum()
```

groups the data by region and calculates total revenue for each region.

- Noida: 960,000 — highest revenue
- Sonipat: 240,000 — lowest revenue

### Answer 4

The first dataset had each vehicle model only once, so grouping would not demonstrate much.

Repeated categories allow `groupby()` to combine multiple records and calculate meaningful category-level totals.

### Answer 5

Noida generated the highest revenue at 960,000, while Sonipat generated the lowest revenue at 240,000.

The business should maintain product availability and dealer support in Noida. For Sonipat, it should investigate demand, vehicle availability, dealer performance, pricing, and promotional activity before deciding on further action.

### Answer 6

We cannot conclude with certainty that poor promotion is the reason for Sonipat’s lower revenue.

Other factors may include:

- Vehicle availability
- Dealer performance
- Customer demand
- Pricing
- Product mix
- Promotional activity

More data and investigation are needed before making a final conclusion.

### Day 2 Result

Score: 11/12 — 92%

---

## Day 3 Answers

### Answer 1

After grouping data, the grouping field may become the index of the result.

`reset_index()` converts that index back into a normal DataFrame column.

### Answer 2

`ascending=False` sorts the rows from highest to lowest based on the selected values.

We used it to display the regions from highest revenue to lowest revenue.

### Answer 3

Matplotlib is a Python library used to create charts and visualizations.

`plt` is the short alias for `matplotlib.pyplot`.

### Answer 4

```python
regional_revenue_df["Region"]
```

provides the category names on the horizontal axis.

```python
regional_revenue_df["Revenue"]
```

provides the numerical values that determine the bar heights.

### Answer 5

We divided Revenue by `100000` to convert rupees into lakhs.

For example:

```text
960000 ÷ 100000 = 9.6 lakhs
```

This made the chart easier to read in an Indian business context.

### Answer 6

```python
plt.title("Revenue by Region")
```

adds a title to the chart.

```python
plt.xlabel("Region")
```

labels the horizontal axis.

```python
plt.ylabel("Revenue (₹ Lakhs)")
```

labels the vertical axis.

```python
plt.show()
```

displays the chart.

### Day 3 Result

Score: 10/12 — 83%

---

## Day 4 Answers

### Answer 1

- `None` represents a missing or unknown value.
- `""` is an empty text string. It looks blank, but Pandas may not automatically treat it as missing.
- `0` is a real numerical value equal to zero, not automatically a missing value.

### Answer 2

`isna()` checks each cell for a missing value and returns `True` or `False`.

`sum()` counts the `True` values and gives the total number of missing values in each column.

### Answer 3

```python
df3["City"] = df3["City"].fillna("Unknown")
```

replaces missing values in the City column with `"Unknown"`.

We used `"Unknown"` because City is a text column and the actual city was not available.

### Answer 4

Salary is a numerical column, so `"Unknown"` would not be suitable.

A value of `0` means zero salary, not missing salary.

The median provides a central value based on the other salaries and is often safer than the average when values may contain unusually high or low amounts.

### Answer 5

A duplicate record is a complete row that appears more than once with the same values.

For practice, we copied the cleaned `df3` DataFrame and added a copy of its first row to create `df4`.

### Answer 6

```python
df4.duplicated()
```

returns a Boolean Series:

- `True` for duplicate rows
- `False` for non-duplicate rows

```python
df4.duplicated().sum()
```

counts the `True` values and returns the total number of duplicate rows.

### Answer 7

```python
drop_duplicates()
```

removes repeated rows from a DataFrame.

We used it to create `df4_clean` without duplicate employee records, so the same record would not be counted twice.

### Answer 8

```python
df4_clean.dtypes
```

shows the data type of every column.

```python
df4_clean["Salary"].astype(int)
```

converts the Salary column to an integer type.

```python
pd.to_datetime(df4_clean["Join_Date"])
```

converts the Join_Date column from text into a proper date-time type.

### Day 4 Result

Score: 14/16 — 87.5%
