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
# Arrays
Arrays are a powerful data structure provided by the `NumPy` library in Python. They allow you to store multiple items of the same type in a single variable and perform efficient mathematical operations on these items.

## Why Use Arrays?
Arrays are particularly useful when you need to perform element-wise operations or calculations on sequences of data. Unlike Python lists, which can contain elements of different types, arrays enforce a single data type for all elements. This consistency allows arrays to be more memory-efficient and to support faster, vectorized operations.

When you want to create an array, you need to use the `numpy.array()` function to combine the elements into an array.

```python
import numpy as np

apple = np.array(["red", "green", "yellow"])
print(apple)
# Output:
# ['red' 'green' 'yellow']
```

An array’s type can be checked with the `dtype` attribute. `apple` is a word, not a number, therefore it is a string.
```python
# Ask for the data type of the array
print(apple.dtype)
# Output:
# dtype('<U6')  # Unicode string of max length 6
```

Another important property of an array is its length. This is the number of elements in the array and can be checked with the `len()` function. In this case, the length is 3. Three values for "red", "green", and "yellow".
```python
# Ask for the length of the array
print(len(apple))
# Output:
# 3
```

An array can only contain values of the same data type.

You can add elements by creating a new array that includes the new elements.
```python
# Add an element
apple = np.append(apple, "brown")
print(apple)
# Output:
# ['red' 'green' 'yellow' 'brown']
```
### Vectorization
In Python, most (but not all!) functions provided by the numpy library are automatically applied to all elements of an array.

When you perform an operation on two arrays of the same length, NumPy will automatically apply the operation element-wise, meaning it performs the operation between the corresponding elements of the arrays. In the next example out arrays contains numbers for calculations not strings.

```python
import numpy as np

# Creating two arrays of the same length
x = np.array([1, 2, 3])
y = np.array([4, 5, 6])

# Performing element-wise addition
result = x + y
print(result)
# Output: [5 7 9]
```