---
title: Merging
header:
  image: /assets/images/unit_images/u08/header.png
  image_description: "noodle"
  caption: "Photo by [congerdesign](https://pixabay.com/de/users/congerdesign-509903/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1312384) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1312384)"
---
To merge data frames based on identifiers rather than the order of the rows, we utilize the `merge()` function in pandas. When merging two data frames, it's essential to designate the column that contains the identifiers for matching by using the `on` argument. This is a crucial step; if you don't set the column by which the data frames should be merged, python will take columns with the same name in both data frames automatically for merging.

{% include figure image_path="/assets/images/unit_images/u08/Merge_LOTR2.png" %}


To create the two data frames from the picture we run this code.


```python
import pandas as pd

# DataFrame 1
df1 = pd.DataFrame({
    'id': ['Frodo', 'Aragorn', 'Legolas', 'Gimli', 'Gandalf'],
    'race': ['Hobbit', 'Human', 'Elf', 'Dwarf', 'Maia']
})
print(df1)

# DataFrame 2
df2 = pd.DataFrame({
    'name': ['Aragorn', 'Frodo', 'Gimli', 'Legolas'],
    'Weapon': ['Sword', 'Ring', 'Axe', 'Bow']
})
print(df2)

# Output:
#         id    race
# 0    Frodo  Hobbit
# 1  Aragorn   Human
# 2  Legolas     Elf
# 3    Gimli   Dwarf
# 4  Gandalf    Maia
#       name Weapon
# 0  Aragorn  Sword
# 1    Frodo   Ring
# 2    Gimli    Axe
# 3  Legolas    Bow
```


Since the column names in both data frames are different, we need to either rename one of the columns to match the other or use the `left_on` and `right_on` parameters in the merge function to specify the columns to merge on. The parameter `how=inner` makes sure to only include rows which have a matching partner in the other data frame.

```python
# Merge DataFrames
merged_df_on = pd.merge(df1, df2, left_on='id', right_on='name', how='inner')

# or

# Rename column in df1
df1.rename(columns={'id': 'name'}, inplace=True)
# Merge DataFrames
merged_df_rename = pd.merge(df1, df2, on='name', how='inner')

# Output:
#      name    race Weapon
# 0    Frodo  Hobbit   Ring
# 1  Aragorn   Human  Sword
# 2  Legolas     Elf    Bow
# 3    Gimli   Dwarf    Axe
```



{% include figure image_path="/assets/images/unit_images/u08/Merge_LOTR1.png" %}



## Test what you've learned so far!

<iframe src="https://geomoer.github.io/moer-h5p-content/h5p-standalone-1.3.x/demo/base-r-unit08-merging.html" width="1090" height="450" frameborder="0" allowfullscreen="allowfullscreen" allow="geolocation *; microphone *; camera *; midi *; encrypted-media *"> </iframe><script src="https://h5p.org/sites/all/modules/h5p/library/js/h5p-resizer.js" charset="UTF-8"></script> 

<!--
## Further reading

add some day
-->
