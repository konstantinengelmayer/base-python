---
title: Sorting
header:
  image: /assets/images/unit_images/u08/header.png
  image_description: "noodle"
  caption: "Photo by [congerdesign](https://pixabay.com/de/users/congerdesign-509903/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1312384) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1312384)"
---


> “It is a capital mistake to theorize before one has data.” — Sherlock Holmes
<!--more-->


#### Sorting lists
Lists in Python can be sorted using the `sort()` method or the `sorted()` function.

The `sort()` method sorts the list in place.
```python
x = [7, 5, 8, 2, 10]
x.sort()
print(x)
# Output:
# [2, 5, 7, 8, 10]
```

The sorted() function returns a new sorted list.
```python
x = [7, 5, 8, 2, 10]
sorted_x = sorted(x)
print(sorted_x)
# Output:
# [2, 5, 7, 8, 10]
```

#### Sorting arrays
Arrays can be sorted using NumPy's `sort()` function.
```python
import numpy as np

x = np.array([7, 5, 8, 2, 10])
sorted_x = np.sort(x)
print(sorted_x)
# Output:
# [ 2  5  7  8 10]
```

#### Sorting data frames
Sorting DataFrames can be accomplished using the `sort_values()` method provided by the pandas library. This method is applied directly to the DataFrame and can sort by one or multiple columns. First we create our data frame.

```python
import pandas as pd

# Sample data
x = [2, 5, 2, 2, 10]
y = ["Z", "D", "R", "A", "O"]
z = [10, 40, 20, 30, 50]

# Creating the DataFrame
df = pd.DataFrame({'X': x, 'Y': y, 'Z': z})
print(df)

# Output:
#     X  Y   Z
# 0   2  Z  20
# 1   5  D  40
# 2   2  R  10
# 3   2  A  30
# 4  10  O  50
```
 Now we sort the data frame by the column x.
```python
df = df.sort_values(by='X')
print(df)
# Output:
# X  Y   Z
# 0   2  Z  20
# 2   2  R  10
# 3   2  A  30
# 1   5  D  40
# 4  10  O  50

```
We can also sort the data frame by multiple columns.
```python
df = df.sort_values(by=['X', 'Z'])
print(df)
# Output:
#     X  Y   Z
# 0   2  Z  10
# 2   2  R  20
# 3   2  A  30
# 1   5  D  40
# 4  10  O  50
```
If we want to undo this, we can use the `sort_index()` method.
```python
df = df.sort_index()
print(df)
# Output:
#     X  Y   Z
# 0   2  Z  20
# 1   5  D  40
# 2   2  R  10
# 3   2  A  30
# 4  10  O  50
```

The sorting works the same if you want to sort the data frame by a column containing character. Then the data frame is sorted alphabetically.
```python
df = df.sort_values(by='Y')
print(df)
# Output:
#   X  Y   Z
# 3   2  A  30
# 1   5  D  40
# 4  10  O  50
# 2   2  R  20
# 0   2  Z  10
```


<!--
## Further reading

add some day
-->
