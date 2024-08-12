---
title: "Object Types"
toc: TRUE
toc_float: TRUE
header:
  image: /assets/images/unit_images/u03/header.png
  image_description: "neon data"
  caption: "Photo by [Franki Chamaki](https://unsplash.com/@franki?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) [from unsplash](https://unsplash.com/s/photos/data?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText)"
---

<!--more-->

# Dataframe
In Python, data frames are provided by the `pandas` library. A data frame is a two-dimensional data structure, similar to a list of equal-length lists. So basically data frames are simple tables we all now.  Each column represents a variable, and each row represents an observation or case. Unlike matrices, data frames can hold columns of different data types (e.g., numeric, string, date, etc.). This makes data frames suitable for storing and working with structured data and allows you to represent real-world datasets with mixed data types in a single structure. Data frames are built with the `pd.DataFrame()` function.

```python
import pandas as pd

# Creating lists
a = ["Peter", "Sabine", "Rachel", "Ray", "Ashley"]
b = [24, 42, 12, 56, 57]
c = [1.54, 1.85, 1.30, 1.97, 1.64]
d = [True, False, False, True, False]

# Creating a data frame from lists with assigned column names
patients = pd.DataFrame({
    'Name': a,
    'Age': b,
    'Height': c,
    'Ill': d
})

print(patients)
# Output:
#     Name  Age  Height    Ill
# 0   Peter   24    1.54   True
# 1  Sabine   42    1.85  False
# 2  Rachel   12    1.30  False
# 3     Ray   56    1.97   True
# 4  Ashley   57    1.64  False
```
In Python, data frames provided by the pandas library have column names (variable names) and row names (often called row labels) that help identify and reference specific variables and observations. You can access columns using the dot operator or square brackets `[]`, and you can access rows by their index or labels.

```r
# Accessing columns
print(patients.Name)  # Using dot operator
print(patients['Name'])  # Using square brackets
# Output:
# 0     Peter
# 1    Sabine
# 2    Rachel
# 3       Ray
# 4    Ashley
# Name: Name, dtype: object

# Accessing rows by index and label
# because the row is at index 0 but is also called 0 we ask for the same
print(patients.iloc[0])  # Accessing the first row
print(patients.loc[0])  # Accessing the row with label 0
# Output:
# Name      Peter
# Age          24
# Height     1.54
# Ill        True
# Name: 0, dtype: object

```

New columns can be directly assigned:
```python
# Adding a new column using direct assignment
patients['Last_Name'] = ['Müller','Schmidt','Smith','Brown','Rodriguez']
print(patients)
# Output:
#      Name  Age  Height    Ill  Last_Name
# 0   Peter   24    1.54   True     Müller
# 1  Sabine   42    1.85  False    Schmidt
# 2  Rachel   12    1.30  False      Smith
# 3     Ray   56    1.97   True      Brown
# 4  Ashley   57    1.64  False  Rodriguez
```