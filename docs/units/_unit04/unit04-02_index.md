---
title: Indexing
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

There are multiple ways to access or replace values in vectors or other data structures. The most common approach is to use “indexing”. This is also referred to as “slicing”.

Note that brackets `[]` are used for indexing, whereas parentheses `( )` are used to call a function.

## Arrays
Here are some examples that show how elements of arrays can be obtained by indexing.

Consider vector `v`:
```python
# load NumPy library
import numpy as np

# Generating some data
v = np.arange(10, 16)
print(v)
# Output:
# [10 11 12 13 14 15]
```
Note that when working with ranges or slicing in python, the ending value is never included. So even if we set a range of 10 to 16 the output values range from 10 to 15.<br>

Now lets start indexing. Let's get the first element of the array and print it.
```python
# Get the first element of a vector
print(v[0])  # Output: 10
```
As you see we used a 0 instead of a 1 to access the first value of the array. This is because python's indexing start with 0. So if we want to access the fourth element we would need to write a 3 like this.

```python
# Accessing the fourth element
print(v[3])  # Output: 13
```
You can also access multiple elements at a time using ranges or another pair of `[]` to chose elements which are not directly next to each other. 
```python
print(v[1:3])  # Output: [11 12]

print(v[[1, 3]]) #  Output: [11, 13]
```
As you see here again the last index of the range (3) is not included in the out. 

You can also use an index to change values

```python
v[0] = 11 # Change position 1 from 10 to 11
print(v) # Output: [11 11 12 13 14 15]

v[[3,5]] = [0,5]
print(v) # Output: [11 11 12  0 14  5]

v[1:6] = -99
print(v) # Output: [ 11 -99 -99 -99 -99 -99]
```

## Matrix
Consider matrix `m`.
```python
import numpy as np

# Creating the matrix
m = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Printing the matrix
print(m)

# Output:
# [[1 2 3]
#  [4 5 6]
#  [7 8 9]]
```

Like arrays, values of matrices can be accessed through indexing. There are different ways to do this, but it is generally easiest to use two numbers in a double index, the first for the row number(s) and the second for the column number(s).

```python
# One value in row 2, column 2
print(m[1, 1])

# Output:
# 5

# Another one in row 1, column 3
print(m[0, 2])

# Output: 
# 3
```

You can also get multiple values at once.

```python
# 2 rows and 2 columns
print(m[0:2, 0:2])

# Output:
# [[1 2]
#  [4 5]]

# Entire row
print(m[1, :])

# Output:
# [4 5 6]

# Entire column
print(m[:, 1])

# Output:
# [2 5 8]
```

You can also use slicing to get specific columns or rows

```python
# Single column
print(m[:, 1])

# Output:
# [2 5 8]

# Two columns
print(m[:, [0, 2]])

# Output:
# [[1 3]
#  [4 6]
#  [7 9]]
```
Setting values of a matrix is similar to how you would do that for an arrays, except that you now need to deal with two dimensions.

```python
# One value
m[0, 0] = 5
print(m)

# Output:
# [[5 2 3]
#  [4 5 6]
#  [7 8 9]]

# A row
m[2, :] = 10
print(m)

# Output:
# [[ 5  2  3]
#  [ 4  5  6]
#  [10 10 10]]
```

## List
Indexing lists can be a bit confusing as you can both refer to the elements of the list, or the elements of the data (perhaps a matrix) in one of the list elements.

```python
# Create a list containing another list, a list of strings, and a NumPy matrix
import numpy as np
e = [[1, 2, 3], ['a', 'b', 'c', 'd'], np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])]

print(e)

# Output:
# [[1, 2, 3], ['a', 'b', 'c', 'd'], array([[1, 2, 3],
#        [4, 5, 6],
#        [7, 8, 9]])]
```

We can access data inside a list element by combining double and single brackets. By using the double brackets, the list structure is dropped.

```python
# Accessing an element of the list (returns a list)
print(e[1])
# Output: ['a', 'b', 'c', 'd']

# Accessing the contents of the list element directly
print(e[1][0])
# Output: 'a'

# Accessing the contents of the matrix
print(e[2][1,1])
# Output: 5
```

## Data.frame
ndexing a DataFrame in Python can be done similarly to indexing matrices and lists, using the pandas library.

First, create a DataFrame from a NumPy array m.

```python
# Create a DataFrame from the matrix
d = pd.DataFrame(m, columns=['a', 'b', 'c'])
print(type(d))
# Output: <class 'pandas.core.frame.DataFrame'>

print(d)
# Output:
#    a  b  c
# 0  1  2  3
# 1  4  5  6
# 2  7  8  9
```

You can extract a column by column number.

```python
# Extract the second column by index
print(d.iloc[:, 1])
# Output:
# 0    2
# 1    5
# 2    8
# Name: b, dtype: int64
```
But you can also extract a column by name

```python
# Extract the second column by name
print(d['b'])
# Output:
# 0    2
# 1    5
# 2    8
# Name: b, dtype: int64
```
You can also use the dot notation or the get method.

```python
# Using dot notation to get the column values
print(d.b)
# Output:
# 0    2
# 1    5
# 2    8
# Name: b, dtype: int64

# Or using the .get method
print(d.get('b'))
# Output:
# 0    2
# 1    5
# 2    8
# Name: b, dtype: int64
```


By default, pandas will drop the DataFrame structure when selecting a single column, returning a Series. To prevent this and keep the DataFrame structure:

```python
# Select a column without dropping the DataFrame structure
print(d[['b']])
# Output:
#    b
# 0  2
# 1  5
# 2  8

# Another way to avoid dropping is to use the loc method
print(d.loc[:, ['b']])
# Output:
#    b
# 0  2
# 1  5
# 2  8
```

Why should you care about this drop business? Well, in many cases R functions want a specific data type, such as a matrix or data.frame and report an error if they get something else. One common situation is that you think you provide data of the right type, such as a data.frame, but that in fact you are providing a vector, because the structure dropped.

## Finding Indices, isin, and match
Sometimes you do not have the indices you need, and so you need to find them. For example, what are the indices of the elements in a vector that have values above 15?

```python
import numpy as np

# Create a numpy array
x = np.arange(10, 21)
i = np.where(x > 15)
print(x)
# Output: [10 11 12 13 14 15 16 17 18 19 20]

print(i)
# Output: (array([6, 7, 8, 9, 10]),)

print(x[i])
# Output: [16 17 18 19 20]
```
So here we looked the indicies of values being bigger than 15. These indicies we can than use to get the values which are bigger than  15. <br>
You can also use a boolean array for indexing.

```python
# Create a boolean array
b = x > 15

print(b)
# Output: [False False False False False False  True  True  True  True  True]

print(x[b])
# Output: [16 17 18 19 20]
```

The np.isin function allows you to check whether each element of an array is in another array. It returns 'True' or 'False' for each element of the first array. With np.where you can than get the indicies which are 'True'

```python
j = np.array([7, 9, 11, 13])
print(np.isin(j, x))
# Output: [False False  True  True]

print(np.where(np.isin(j, x)))
# Output: (array([2, 3]),)
```


<!--
## Further reading

add some day
-->
