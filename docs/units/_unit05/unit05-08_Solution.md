---
title: "Solution to Exercise 1"
toc: TRUE
toc_float: TRUE
published: true
header:
  image: /assets/images/unit_images/u03/header.png
  image_description: "neon data"
  caption: "Photo by [Franki Chamaki](https://unsplash.com/@franki?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) [from unsplash](https://unsplash.com/s/photos/data?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText)"
---

See if you were right in exercise 1!

### Tasks
**1.** Calculate the root square of 10 + 6.<br>
```python
(10+6)**2
```
**2.** Create arrays for size, height and states <br>
<br>
size: 1.67, 1.8, 1.58, 1.83, 1.65, 1.74, 1.8, 1.6, 1.76, 1.8 <br>
weight: 62, 78, 56, 85, 58, 70, 70, 120, 62, 90 <br>
state: NRW, Bayern, Sachsen, Hessen, Hessen, MV, Hessen, Brandenburg, Hessen, Berlin<br>
<br>
```python
import numpy as np
size = np.array([1.67, 1.8, 1.58, 1.83, 1.65, 1.74, 1.8, 1.6, 1.76, 1.8])
weight = np.array([62, 78, 56, 85, 58, 70, 70, 120, 62, 90])
state = np.array(["NRW", "Bayern", "Sachsen", "Hessen", "Hessen", "MV", "Hessen", "Brandenburg", "Hessen", "Berlin"])
 ```
**3.** Use the arrays you just created to create a DataFrame with the columns size, weight, and state.
```python
import pandas as pd
df = pd.DataFrame({'size' : size, 'weight' : weight, 'state' :state})
print(df)
# Output:
#    size  weight        state
# 0  1.67      62          NRW
# 1  1.80      78       Bayern
# 2  1.58      56      Sachsen
# 3  1.83      85       Hessen
# 4  1.65      58       Hessen
# 5  1.74      70           MV
# 6  1.80      70       Hessen
# 7  1.60     120  Brandenburg
# 8  1.76      62       Hessen
# 9  1.80      90       Berlin
```