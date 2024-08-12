---
title: Subsetting
toc: TRUE
toc_float: TRUE
header:
  image: /assets/images/unit_images/u04/header.png
  image_description: "index"
  caption: "Photo by [Maksym Kaharlytskyi](https://unsplash.com/@qwitka?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) from [Unsplash](https://unsplash.com/?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText)"
---

<!--more-->

> “Big data is at the foundation of all of the megatrends that are happening today, from social to mobile to the cloud to gaming.” – Chris Lynch

---

When you are working with a large data set, you are often only interested in a small part of it for your analysis. So how do you sort out all the variables and observations and extract only the ones you need? Well, python has several ways of doing this in a process it calls "subsetting".

The most basic way of subsetting a data frame in R is by using square brackets such that in:

```
data[x,y]
```
`data` is the data frame we want to subset. `x` consists of the rows we want returned, and `y` consists of the columns we want returned. Let’s pull some data from the dataset `mtcars` and see how this is done on a real data set.

Now, let’s suppose we only need *mpg, hp* and *gear* to show the relationship between fuel consumption, horsepower and number of gears. However, we only need data seperated by the kind of transmission (am): 0 = automatic, 1 = manual. Here’s the basic way to retrieve that data in R:

```python
import pandas as pd

# Load the mtcars dataset
mtcars = pd.read_csv('https://raw.githubusercontent.com/selva86/datasets/master/mtcars.csv')

# Extracting data
manual1 = mtcars[mtcars['am'] == 1].iloc[:, [0, 3, 9]]
automatic1 = mtcars[mtcars['am'] == 0].iloc[:, [0, 3, 9]]
```

With ` mtcars[mtcars['am'] == 1]` we select all rows which have a 1 in the column am which stands for a manual car. With `.iloc[:,0, 3, 9]` we then select the columns we are interested in.

S0 we separated the record (mtcars) according to the type of transmission (mtcars$am==1) and **used only** the first (mpg), fourth (hp) and tenth (gears) columns.

You can also specify columns to drop instead of selecting columns to keep.
```python
# Dropping data
manual2 = mtcars[mtcars['am'] == 1].drop(columns=['cyl', 'disp', 'drat', 'wt', 'qsec', 'vs', 'carb'])
automatic2 = mtcars[mtcars['am'] == 0].drop(columns=['cyl', 'disp', 'drat', 'wt', 'qsec', 'vs', 'carb'])
```

---

## subseting functionality
The `query` method and column selection can be used to subset a DataFrame without knowing the row and column indices.
The `query` method takes a single string argument that represents the condition for filtering the DataFrame. Additionally, you can specify the columns you want to select by chaining the loc method.

```python
# The query meothd
manual3 = mtcars.query('am == 1')[['mpg', 'hp', 'gear']]
automatic3 = mtcars.query('am == 0')[['mpg', 'hp', 'gear']]
```

In the following example, we select by different values:

First all rows that have a value of horsepower (hp) between 100 and 200.
Second all rows that have a value of horsepower greater or equal to 150 AND are automatic.
Third all rows that have a value of horsepower greater or equal to 250 OR have less than 4 gears.
We keep the mpg, hp and gear columns for all three.

```python
# hp between 100 and 200
hp = mtcars.query('100 <= hp < 200')[['mpg', 'hp', 'gear']]

# hp >=150 AND automatic
hp_am = mtcars.query('hp >= 150 & am == 0')[['mpg', 'hp', 'gear', 'am']]

# hp >=250 OR <4 gears
hp_gear = mtcars.query('hp >= 250 | gear < 4')[['mpg', 'hp', 'gear', 'am']]
```

---

## Random sample

Generally speaking, whenever we introduce randomness in Python, we should set a random seed to make our code reproducible. The `np.random.seed()` function sets the starting number used to generate a sequence of random numbers. This ensures that you get the same result if you start with that same seed each time you run the same process. The seed is an arbitrary number. You can then use the `sample()` method from pandas to take a random sample of size n from a DataFrame either with or without replacement.

```python
# Setting the seed for reproducibility
np.random.seed(1234)
```

Random sample of a data frame:
```python
# Take a random sample of 10 rows without replacement
sampled_df = mtcars.sample(n=10, replace=False)

print(sampled_df)
```




<!--
## Further reading

add some day
-->
