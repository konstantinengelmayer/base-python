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

You may like to store information of various data types like character, integer, floating point, Boolean etc. Based on the data type of a object, the operating system allocates memory and decides what can be stored in the reserved memory.

The objects are assigned with Python objects, and the data type of the Python object becomes the data type of the object. There are many types of Python objects. The ones we use the most are:

*	Lists
*	Data Frames
*	Matrices
*	Arrays

# Objects
In Python, objects serve a fundamental role in any program. They hold the data we work with and the results of our computations. Objects also allow us to label data with meaningful names, enhancing code readability and comprehension. You can think of objects as containers that store information, similar to how a drawer holds items in the picture below. Their primary purpose is to label and store data, making it accessible throughout the code. 
- A drawer labeled 'Animals' could contain numbers, which could represent counts of animals.
- A drawer labeled 'Patients' contains text, holding names or descriptions of patients.
{% include figure image_path="/assets/images/unit_images/u03/container.webp" %}

**How to name an object?**

> “All things are defined by names. Change the name, and you change the thing” — Terry Pratchett, Pyramids

Even though data is very diverse, objects cannot take every name. This is because they must be unique to the computer. They can contain letters, numbers and underscores ( _ ), though the latter cannot be used at the beginning of the name. All other characters and spaces are not allowed. This restriction is important because R has to understand the input data, furthermore it has to be unique for the program. For example, if minus signs (-) were allowed for naming (which they are not!), there would be an ambiguity with the name `all-animals`. Python would not know whether we meant the object `all-animals` or whether we wanted to subtract the object `animals` from the object `all`.

Instead, we could call it `all_animals`, `AllAnimals`, `allanimals`, `Allanimals` or `allAnimals`.

Note that python distinguishes between upper and lower case for names. `allAnimals` and `AllAnimals` are not the same object and it is not possible to switch them.
You should generally not use names, which are reserved for functions (e.g `type()`). Try to find meaningful names, but try to make them relatively short, too.

**How to define objects?**

The assignment operator is the equal sign `=` and is used to assign values or characters to objects.
```r
# Assign the value 4 to object x
x = 4

# Assign the name "Peter" to object y
y = "Peter"

# To show the content of a variable we can do this
y
# Output: 'Peter'

x
# Output: 4
```

-----
# Arrays
If you want to store more than one value in an object, you need an array. It is a basic data structure and contains elements of the same type. The data types can be logical, integer, float, and string.

When you want to create an array with more than one element, you need to use the `numpy.array()` function to combine the elements into an array.

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

When you perform an operation on two arrays of the same length, NumPy will automatically apply the operation element-wise, meaning it performs the operation between the corresponding elements of the arrays.

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
-----------

# Dataframe
In Python, data frames are provided by the `pandas` library. A data frame is a two-dimensional data structure, similar to a list of equal-length lists. Each column represents a variable, and each row represents an observation or case. Unlike matrices, data frames can hold columns of different data types (e.g., numeric, string, date, etc.). This makes data frames suitable for storing and working with structured data and allows you to represent real-world datasets with mixed data types in a single structure. Data frames are built with the `pd.DataFrame()` function.

```python
import pandas as pd

# Creating lists
a = ["Peter", "Sabine", "Rachel", "Ray", "Ashley"]
b = [24, 42, 12, 56, 57]
c = [1.54, 1.85, 1.30, 1.97, 1.64]
d = [True, False, False, True, False]

# Creating a data frame from lists with assigned column names
patients = pd.DataFrame({
    'Name': a,
    'Age': b,
    'Height': c,
    'Ill': d
})

print(patients)
# Output:
#     Name  Age  Height    Ill
# 0   Peter   24    1.54   True
# 1  Sabine   42    1.85  False
# 2  Rachel   12    1.30  False
# 3     Ray   56    1.97   True
# 4  Ashley   57    1.64  False
```
In Python, data frames provided by the pandas library have column names (variable names) and row names (often called row labels) that help identify and reference specific variables and observations. You can access columns using the dot operator or square brackets `[]`, and you can access rows by their index or labels.

```r
# Accessing columns
print(patients.Name)  # Using dot operator
print(patients['Name'])  # Using square brackets
# Output:
# 0     Peter
# 1    Sabine
# 2    Rachel
# 3       Ray
# 4    Ashley
# Name: Name, dtype: object

# Accessing rows by index and label
# because the row is at index 0 but is also called 0 we ask for the same
print(patients.iloc[0])  # Accessing the first row
print(patients.loc[0])  # Accessing the row with label 0
# Output:
# Name      Peter
# Age          24
# Height     1.54
# Ill        True
# Name: 0, dtype: object

```

New columns can be directly assigned:
```python
# Adding a new column using direct assignment
patients['Last_Name'] = ['Müller','Schmidt','Smith','Brown','Rodriguez']
print(patients)
# Output:
#      Name  Age  Height    Ill  Last_Name
# 0   Peter   24    1.54   True     Müller
# 1  Sabine   42    1.85  False    Schmidt
# 2  Rachel   12    1.30  False      Smith
# 3     Ray   56    1.97   True      Brown
# 4  Ashley   57    1.64  False  Rodriguez
```

-----
# Matrix
A matrix is a two-dimensional rectangular data set. You can create and manipulate matrices using the `numpy` library.

### Create a Matrix
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
---

# Lists
A list is an object which can contain many different types of elements inside it, such as arrays, a matrix, functions, and even another list inside it. The list is typically created using square brackets `[]`. Unlike arrays, list elements do not need to have equal length and the same data types.

```python
# Creating a list with multiple elements
# Create a list
list1 = [[2, 5, 3], 21.3, sum]

# Print the list
print(list1)

# Output: list1 = [[2, 5, 3], 21.3, sum]
```

You can access list elements using square brackets `[]`. Using single square brackets returns the element while preserving its structure as a list. To access the value inside, you again use `[]` to access the values

```python
# Accessing elements
print(list1[0])  # Output: [2, 5, 3]
print(list1[1])  # Output: 21.3
print(list1[2])  # Output: <built-in function sum>

# Accessing elements within a sublist
print(list1[0][1])  # Output: 5
```

# Multidimensional Arrays
Multidimensional arrays are arrays that have more than two dimensions. These can be created and manipulated using the `numpy` library. They are useful for handling complex data structures like matrices, tensors, and higher-dimensional data.

While lists in Python are flexible and can hold different types of elements, including other lists to create nested structures, they are not optimized for numerical operations and become cumbersome and inefficient for large datasets. Similarly, matrices are inherently two-dimensional and cannot naturally extend to higher dimensions needed for complex data structures. Multidimensional arrays are basically matrices stacked behind each other like this:
```python
import numpy as np

# Create a 3D array (2 layers, each with 3 rows and 4 columns)
array_3d = np.array([
    [
        [1, 2, 3, 4],
        [5, 6, 7, 8],
        [9, 10, 11, 12]
    ],
    [
        [13, 14, 15, 16],
        [17, 18, 19, 20],
        [21, 22, 23, 24]
    ]
])

print(array_3d)
# Output:
# [[[ 1  2  3  4]
#   [ 5  6  7  8]
#   [ 9 10 11 12]]
#
#  [[13 14 15 16]
#   [17 18 19 20]
#   [21 22 23 24]]]
```