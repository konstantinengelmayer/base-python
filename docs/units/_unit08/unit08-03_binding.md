---
title: Binding
header:
  image: /assets/images/unit_images/u08/header.png
  image_description: "noodle"
  caption: "Photo by [congerdesign](https://pixabay.com/de/users/congerdesign-509903/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1312384) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1312384)"
---

> “In God we trust, all others bring data.” — W Edwards Deming
<!--more-->

When thinking about combining two data frames one has to distinguish between
merging them by the values given in a specific column or consecutively putting
them together just rows after rows. Here will bind these data frames together by row and by column

For the following examples, we will use these two data frames.

```python
import pandas as pd

# DataFrame 1
x1 = [1, 2, 3, 4, 5]
y1 = [1.4, 2.5, 3.6, 4.0, 5.5]
z1 = ["A", "B", "C", "D", "E"]

df1 = pd.DataFrame({'X': x1, 'Y': y1, 'Z': z1})

# DataFrame 2
y2 = [14, 25, 36, 40, 55]
x2 = [100, 200, 300, 400, 500]
z2 = ["A", "C", "E", "D", "B"]

df2 = pd.DataFrame({'X': x2, 'Y': y2, 'Z': z2})
```
To concatenate two DataFrames row-wise, we use the `concat()` function provided that both DataFrames have the same column names and the same number of columns.

```python
# Concatenate row-wise
dfr = pd.concat([df1, df2], ignore_index=True)
print(dfr)
# Output:
#      X     Y  Z
# 0    1   1.4  A
# 1    2   2.5  B
# 2    3   3.6  C
# 3    4   4.0  D
# 4    5   5.5  E
# 5  100  14.0  A
# 6  200  25.0  C
# 7  300  36.0  E
# 8  400  40.0  D
# 9  500  55.0  B
```

Note, that it is not necessary that the columns are in the same order since the
concatenation is done by the column names, not the column sequence.

When you want to bind column column-wise you can also use the `concat()` function. Here you need to set the `axis` parameter to 1.

```python
# Bind the DataFrames by columns
dfc = pd.concat([df1, df2], axis=1)
print(dfc)

# Output:
#    X    Y  Z    X   Y  Z
# 0  1  1.4  A  100  14  A
# 1  2  2.5  B  200  25  C
# 2  3  3.6  C  300  36  E
# 3  4  4.0  D  400  40  D
# 4  5  5.5  E  500  55  B
```

<!--
## Further reading

add some day
-->
