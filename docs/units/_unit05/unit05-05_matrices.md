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

# Matrix
A matrix is a two-dimensional rectangular data set that is particularly useful for mathematical and scientific computations. Matrices are widely used in areas such as linear algebra, physics, computer graphics, and machine learning. You can create and manipulate matrices using the `numpy` library in Python.

## Why Use Matrices?
Matrices are ideal for representing and performing operations on multi-dimensional data, such as performing linear transformations, solving systems of linear equations, or working with multi-dimensional datasets in scientific computing. They allow for efficient storage and computation, especially when dealing with large-scale numerical data.

## Difference Between Matrices and Data Frames
While matrices and data frames may seem similar, especially when considering their two-dimensional structure, they serve different purposes:

- **Matrices**: Matrices are homogeneous, meaning all elements must be of the same data type. They are optimized for numerical operations and are often used in mathematical and scientific contexts.

- **Data Frames**: Data Frames, which are provided by the `Pandas` library, are more flexible. They can store data of different types (e.g., integers, floats, strings) in different columns. Data Frames are typically used for data manipulation and analysis tasks, such as handling tabular data, where you need to perform operations on different types of data.

## Create a Matrix
You can create a matrix using the `numpy.array()` function. Here is an example:
```python
import numpy as np

# Create a matrix
M = np.array([['a', 'a', 'b'], ['c', 'b', 'a'], ['a', 'b', 'c']])
print(M)
# Output:
# [['a' 'a' 'b']
#  ['c' 'b' 'a']
#  ['a' 'b' 'c']]
```

You can also use the `reshape` method. The matrix will be created rowwise by default:
```python
# Create a matrix with row-wise filling
M = np.array(['a', 'a', 'b', 'c', 'b', 'a','a','b','c']).reshape(3, 3)
print(M)
# Output:
# [['a' 'a' 'b']
#  ['c' 'b' 'a']
#  ['a' 'b' 'c']]
```

## Calculations with Matrices
One of the main advantages of matrices is their ability to efficiently perform mathematical operations. `NumPy` allows you to perform element-wise operations or more complex operations such as matrix multiplication.
```python
import numpy as np

# Create two matrices
A = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
B = np.array([[9, 8, 7], [6, 5, 4], [3, 2, 1]])

# Element-wise addition
C = A + B
print("Element-wise addition:\n", C)
# Output:
# [[10 10 10]
#  [10 10 10]
#  [10 10 10]]

# Element-wise multiplication
D = A * B
print("Element-wise multiplication:\n", D)
# Output:
# [[ 9 16 21]
#  [24 25 24]
#  [21 16  9]]
```