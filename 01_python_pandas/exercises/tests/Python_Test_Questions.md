# Python and Pandas Test Questions

## Day 1 Test

### Question 1 of 8

What does this line do?

```python
import pandas as pd
```

Please explain it in your own words.

### Question 2 of 8

What is the purpose of this code?

```python
data = {
    "Vehicle Model": ["A1", "B1", "C1"],
    "UnitSold": [12, 10, 8],
    "Revenue": [360000, 300000, 240000]
}
```

Explain what `data`, the curly brackets `{}`, the column names, and the square brackets `[]` represent.

### Question 3 of 8

What does this line do?

```python
df = pd.DataFrame(data)
```

Also explain what `df` represents after this line runs.

### Question 4 of 8

If a DataFrame contains 5 rows and 4 columns, what will this code return?

```python
df.shape
```

What do the two numbers represent?

### Question 5 of 8

What information does this code provide?

```python
df.info()
```

Name at least three things it can show us.

### Question 6 of 8

Assume the DataFrame has a column named `Revenue`.

Write the Pandas code to calculate the total revenue.

Use this format:

```python
df[...].sum()
```

### Question 7 of 8

What is the difference between these two methods?

```python
df["Revenue"].mean()
```

and

```python
df["Revenue"].max()
```

Explain what each one calculates.

### Question 8 of 8

What does this code do?

```python
df[df["Revenue"] > 300000]
```

Explain:

1. What does `df["Revenue"] > 300000` produce?
2. What does the outer `df[...]` do?

---

## Day 2 Test

### Question 1 of 6

What does this code do?

```python
df2.groupby("Vehicle Model")["Revenue"].sum()
```

Explain the purpose of:

1. `groupby("Vehicle Model")`
2. `["Revenue"]`
3. `.sum()`

### Question 2 of 6

What would this code calculate?

```python
df2.groupby("Vehicle Model")["UnitSold"].sum()
```

What result would you expect for:

- A1
- B1
- C1

### Question 3 of 6

What would this code calculate?

```python
df2.groupby("Region")["Revenue"].sum()
```

Which region had the highest revenue, and which region had the lowest revenue?

### Question 4 of 6

Why did we create a second dataset with repeated vehicle models and regions for Day 2?

Explain why repeated categories are useful when using `groupby()`.

### Question 5 of 6

The regional revenue results were:

| Region | Revenue |
|---|---:|
| Noida | 960,000 |
| Delhi | 660,000 |
| Gurugram | 450,000 |
| Sonipat | 240,000 |

Write two business observations based on this result. One should mention the highest-performing region, and one should mention the lowest-performing region.

### Question 6 of 6

Sonipat has the lowest revenue in this dataset.

Can we conclude with certainty that the reason is poor promotion?

Explain why or why not.

---

## Day 3 Test

### Question 1 of 6

After grouping revenue by region, why did we use:

```python
reset_index()
```

Explain what changed in the result after using it.

### Question 2 of 6

What does this argument do?

```python
ascending=False
```

Why did we use it when sorting regional revenue?

### Question 3 of 6

What is Matplotlib, and what does `plt` represent when we write:

```python
import matplotlib.pyplot as plt
```

### Question 4 of 6

In this chart code:

```python
plt.bar(
    regional_revenue_df["Region"],
    regional_revenue_df["Revenue"]
)
```

What does each of these two parts represent?

1. `regional_revenue_df["Region"]`
2. `regional_revenue_df["Revenue"]`

### Question 5 of 6

Why did we divide `Revenue` by `100000` before creating the chart?

Explain what happens to a value such as `960000`.

### Question 6 of 6

What does this code do?

```python
plt.title("Revenue by Region")
plt.xlabel("Region")
plt.ylabel("Revenue (₹ Lakhs)")
plt.show()
```

Explain the purpose of each line.
