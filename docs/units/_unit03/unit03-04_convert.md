---
title: "Converting Objects"
header:
  image: /assets/images/unit_images/u03/header.png
  image_description: "neon data"
  caption: "Photo by [Franki Chamaki](https://unsplash.com/@franki?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) [from unsplash](https://unsplash.com/s/photos/data?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText)"
---
<!--more-->

> “Errors using inadequate data are much less than those using no data at all.” – Charles Babbage

---

*How to convert arrays, see Unit 2: [Converting Types of Data](/moer-base-r/unit02/unit02-06_convert.html)*

* Use `isinstance` to test for data type. Returns True or False.
* Use `astype` to explicitly convert it.

|   | to array | to matrix | to dataframe |
|------------|-------------|-------------|-------------|
| <b>from array</b> | np.array([x, y]) | np.column_stack((x, y)) <br> np.row_stack((x, y)) | pd.DataFrame({'x': x, 'y': y}) |
| <b>from matrix</b>  | np.array(mymatrix).flatten()  |  | pd.DataFrame(mymatrix) |
| <b>from dataframe</b>  |  | df.values | |

The functions `np.row_stack()` and `np.column_stack()` can be used to bind arrays together. `np.row_stack` arranges the arrays row by row, `np.column_stack` arranges them column by column.

```python
import numpy as np

v1 = np.array([1, 2, 3])
v2 = np.array([4, 5, 6])

print(np.row_stack((v1, v2)))
# Output:
# [[1 2 3]
#  [4 5 6]]

print(np.column_stack((v1, v2)))
# Output:
# [[1 4]
#  [2 5]
#  [3 6]]
```
<!--more-->

<!--
## Further reading

add some day
-->
