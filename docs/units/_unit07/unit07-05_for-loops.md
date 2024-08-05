---
title: For-loops
toc: TRUE
toc_float: TRUE
header:
  image: /assets/images/unit_images/u07/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---

For-loops are the mother of all repeating structures which enable the execution of certain code blocks for multiple times. For-loops are useful if the number of necessary repetitions is known at the starting time of the loop (which is not necessarily the starting time of the program!).

In for loops, the number of repeated executions is given at the start time either by a variable which is defined during the runtime of the previous code or by a constant supplied by the programmer. Imaging that we know already how many times the loop has to be repeated, one can implement it simply as:

```python
for i in range(7, 11):
    print(i)
# Output:
# 7
# 8
# 9
# 10

# Remember that the last number of a range is excluded
```
Note that the variable i which controls the for loop must not be changed within the loop.

Of course, you can nest for loops:

```python
for a in range(7, 11):
    print(f"Outer loop value of a: {i}")  # f-string with {i} embedded
    if i < 10:
        lower_border = i + 1
    else:
        lower_border = i
    for c in range(10, lower_border - 1, -1): # range(start, stop, step size)
        print(f"   Inner loop value of c: {j}")  # f-string with {j} embedded
# Outer loop value of a: 7
#    Inner loop value of c: 10
#    Inner loop value of c: 9
#    Inner loop value of c: 8
# Outer loop value of a: 8
#    Inner loop value of c: 10
#    Inner loop value of c: 9
# Outer loop value of a: 9
#    Inner loop value of c: 10
# Outer loop value of a: 10
#    Inner loop value of c: 10
```

The loop might look complicated but the reason for that is just the if-else statement. It is necessary since the second loop must run from `c` to the integer value just larger than `a` (i.e. 8, 9, 10). Therefore, `a` must be increased by 1 if it is smaller than 10 but stay 10 if it equals 10.

Instead of defining the number of repetitions in the for loop statement, one can also use any vector variable. The number of iterations will always be equal to the length of the vector. This is not surprising, since the `range` function used so far also simply returns an iterable, e.g.:

```r
t = range(7, 11)
print(t)
# Output: 
# 7  8  9 10
```

As obvious from the above examples, the iteration variable (i.e. a or c in our examples above ) is set to the first value of the vector during the first iteration, then to the second value during the second iteration and so on. Since the number of repetitions is defined by the length of the control vector and not by the values within it, one can also use a vector with e.g. characters to construct a for loop:

```python
letters = ["A", "B", "C", "D"]
for elements in letters:
    print(elements)
# Output:
# A
# B
# C
# D
```

**Important:** while this behavior is useful for programming pros, it might be very confusing for greenhorns. Therefore you can just stick to using numbers as iteration elements. The above for loop can be implemented using numbers as follows:

```python
for i in range(4):
    print(letters[i])
# Output:
# A
# B
# C
# D
```

If you want to use this for arbitrary lengths of vector a, just pass the length of the vector into the `seq` function:

```python
for i in range(len(letters)):
    print(letters[i])
# Output:
# A
# B
# C
# D
```

{% include figure image_path="/assets/data/data/for_loop.gif" caption="Animation of the plot process" %}



## Modifying an existing variable in a loop
You can also modify an existing variable inside a for and while loop.
Let's just add an "x" to each entry of variable letters:

```r
for i in range(len(letters)):
    letters[i] = letters[i] + "x"
print(letters)
# Output:
# ['Ax', 'Bx', 'Cx', 'Dx']
```

If you want to get some feedback for each iteration while a loop is running, try to add a line like:

```python
print(f"Current iterator: {i} | Current content of object: {a}")
```


Of course the same is possible for data frames. Let's make an example where we have the following data frame:

```python
import pandas as pd

a = ["A", "B", "C", "A", "B", "A", "A"]
b = ["X", "X", "X", "X", "Y", "Y", "Y"]
c = [1, 2, 3, 4, 5, 6, 7]
d = [10, 20, 30, 40, 50, 60, 70]
df = pd.DataFrame({'Cat1': a, 'Cat2': b, 'Val1': c, 'Val2': d})
```

We now want to modify this data frame in that way that the characters of columns Cat1 and Cat2 are converted to lower case and the values of Val1 and Val2 are converted to their square root. Therefore we must iterate over each column and then we can apply the `str.lower` function to all rows of the first two columns and the `sqrt` function to all entries of the last two columns. While we could use `range(4)` as control vector, we can also directly iterate over the column names to achieve the same result:
```python
import numpy as np

for col in df.columns:
    if df[col].dtype == 'object':  # 'object' dtype indicates the column contains strings
        df[col] = df[col].str.lower()  # Convert to lowercase
    elif df[col].dtype == 'int64':  # Check if the column contains integer values
        df[col] = np.sqrt(df[col])  # Apply square root
```

As you can see, we iterate over the columns of the data frame by using the column names. If the actual column contains strings (checked by `df[col].dtype == 'object'`), the content of the column is converted to lower case and the original column content is overwritten. If the actual column contains integer values (checked by `df[col].dtype == 'int64'`), the content of this column is converted to its square root and the original column content is overwritten.

In the end, the data frame looks like this:

```python
print(df)

# Output:
#  Cat1 Cat2      Val1      Val2
# 0    a    x  1.000000  1.778279
# 1    b    x  1.189207  2.114743
# 2    c    x  1.316074  2.340347
# 3    a    x  1.414214  2.514867
# 4    b    y  1.495349  2.659148
# 5    a    y  1.565085  2.783158
# 6    a    y  1.626577  2.892508
```


## Building a new variable with a loop

The above examples show how to modify an existing variable. If you want to keep your original values but safe the results in a new variable, you have to define it first outside the loop. Afterwards you modify it within the loop so
it is similar to the task above.

For example, if you want to convert the elements of vector a to lower case and store the results in another vector, the following would be necessary:

```python
a = ["A", "B", "C", "A", "B", "A", "A"]
test = []  # this is an empty list
for i in range(len(a)):
    test.append(a[i].lower())

print(test)
# Output:
# ['a', 'b', 'c', 'a', 'b', 'a', 'a']
```
Please note that this example can of course easily implemented without a loop so just take it as a simple illustration.

If you want to construct a data frame, it is just a little more complicated. Let's get back to the original data frame used in the example just above:

```python
a = ["A", "B", "C", "A", "B", "A", "A"]
b = ["X", "X", "X", "X", "Y", "Y", "Y"]
c = [1, 2, 3, 4, 5, 6, 7]
d = [10, 20, 30, 40, 50, 60, 70]
df = pd.DataFrame({'Cat1': a, 'Cat2': b, 'Val1': c, 'Val2': d})
```

We simply initialize the columns with so many rows as we find in the source data frame.

Let's start with the loop:

```python
# Initialize a new DataFrame with the same structure
df_new = pd.DataFrame(index=df.index, columns=df.columns)

# Loop through each column and apply the transformation
for col in df.columns:
    if df[col].dtype == 'object':  # 'object' dtype indicates the column contains strings
        df_new[col] = df[col].str.lower()  # Convert to lowercase
    elif df[col].dtype == 'int64':  # Check if the column contains integer values
        df_new[col] = np.sqrt(df[col])  # Apply square root
```

The only difference to the example above is that the result of the conversions are not stored in the original data frame but in our newly created one.
Let's have a look at its content:

```r

print(df_new)

# Output:
#  Cat1 Cat2      Val1      Val2
# 0    a    x  1.000000  1.778279
# 1    b    x  1.189207  2.114743
# 2    c    x  1.316074  2.340347
# 3    a    x  1.414214  2.514867
# 4    b    y  1.495349  2.659148
# 5    a    y  1.565085  2.783158
# 6    a    y  1.626577  2.892508
```

Looks good.

## DIY loops - some tipps

Sometimes it can be a little overwhelming to write a loop from top to bottom. That's why it makes sense to tackle the whole thing piece by piece. The following approach might be helpful:

1. Start by setting up an empty for loop, establishing the structure for your iterative process. This initial step helps maintain proper text indentation and structure in your code.

2. Take one piece of your data and define it as your data source.

3. Write down all the operations you want to perform within the loop.

4. Identify and handle replaceable elements within your loop. These are parts of your code that may change during each iteration. Use variables or placeholders to represent these elements, enhancing code flexibility and readability.

5. Think about how you want to save the output of each iteration. Create a result container, such as a list or DataFrame, outside the loop, and store the results there.

6. Consider using vectorized operations when possible to improve loop efficiency and reduce code complexity.

7. Debug and test your loop incrementally, checking for errors and unexpected behavior after each iteration. Depending on the complexity of the data, the loop may not be complete. Missing data, for example, often leads to an index out of range error. To eliminate these errors bit by bit, you can use the print(i) command to specify the point at which the loop stops, and continue to process the data or add conditions accordingly.

{% include figure image_path="/assets/data/data/for_loop2.gif" caption="Animation of the plot process" %}


## Test what you've learned so far!

<iframe src="https://geomoer.github.io/moer-h5p-content/h5p-standalone-1.3.x/demo/base-r-unit07-forloops.html" width="1090" height="600" frameborder="0" allowfullscreen="allowfullscreen" allow="geolocation *; microphone *; camera *; midi *; encrypted-media *"> </iframe><script src="https://h5p.org/sites/all/modules/h5p/library/js/h5p-resizer.js" charset="UTF-8"></script> 






