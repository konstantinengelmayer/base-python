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

The objects are assigned with R-Objects and the data type of the R-object becomes the data type of the object. There are many types of R-objects. The frequently used ones are:

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

# Lists
If you want to store more than one value to an object you need a list. It is a basic data structure and contains elements of the same or different data type.

When you want to create a list with more than one element, you use square brackets `[]` to combine the elements into a list.


```python
# Creating a list with multiple elements
apple = ["red", "green", "yellow"]
print(apple)  
# Output: ['red', 'green', 'yellow']
```

You can check the type of the list using the type() function.

```python
# Checking the type of the list
print(type(apple))  
# Output: <class 'list'>
```

Another important property of a list is its length. This is the number of elements in the list and can be checked with the len() function. In this case, the length is 3, for "red", "green", and "yellow".

```python
print(len(apple))  
# Output: 3
```

A list can contain values of different data types, unlike R vectors.

You can add elements using the append() method or by concatenating lists.

```python
# Adding an element
apple.append(10)
print(apple)  
# Output: ['red', 'green', 'yellow', 10]

# Adding multiple elements
apple += ["blue", "5"]
print(apple)  
# Output: ['red', 'green', 'yellow', 'brown', 'blue', '10, 'blue', 5]
```

If you need to repeat an element of a list several times, you can use the multiplication operator `*`:

```python
# Repeat elements
applebucket = apple * 3
print(applebucket)
# Output: ['red', 'green', 'yellow', 'brown', 'blue', '10, 'blue', 5, 'red', 'green', 'yellow', 'brown', 'blue', '10, 'blue', 5, 'red', 'green', 'yellow', 'brown', 'blue', '10, 'blue', 5]
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
```r
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
A matrix is a two-dimensional rectangular data set. It can be created using a vector input to the `matrix()` function.
`nrow` stands for 2 rows and `ncol` for 3 columns. All data within a matrix must be of the same data type.

```r
# Create a matrix.
M = matrix(c('a','a','b','c','b','a'), nrow = 2, ncol = 3)
print(M)
    [,1] [,2] [,3]
[1,] "a"  "b"  "b" 
[2,] "a"  "c"  "a" 

```
When we execute the above code, it produces the following result − Notice that by default, the first column is first filled from top to button, then the second column and so on.


it follows this pattern:

{% include figure image_path="/assets/images/unit_images/u03/matrix_direction.png" %}

If you want to change this, set byrow=FALSE

```r

M = matrix(c('a','a','b','c','b','a'), nrow = 2, ncol = 3, byrow = TRUE)
M
     [,1] [,2] [,3]
[1,] "a"  "a"  "b"
[2,] "c"  "b"  "a"
```
Columns and rows can be attached using __cbind()__ and __rbind()__, respectively.
With __nrow()__ and __ncol()__, you can return the number of rows and columns, respectively.
As in dataframes, you can add names to your columns and row. In contrast to dataframes, however, you cannot address a column with by __”$”__.

---

# Array
Arrays are the objects which can store data in more than two dimensions. For example − If we create an array of dimension (2, 3, 4) then it creates 4 rectangular matrices each with 2 rows and 3 columns. Arrays can store only one data type.

An array is created using the array() function. It takes vectors as input and uses the values in the dim parameter to create an array.

```r
# create an array with numbers from 1 to 24 with the dimensions of 3 rows, 4 columns and 2 "tables".
my.array <- array(1:24, dim=c(3,4,2))

my.array
, , 1
   [,1] [,2] [,3] [,4]
[1,]  1  4  7  10
[2,]  2  5  8  11
[3,]  3  6  9  12
, , 2
   [,1] [,2] [,3] [,4]
[1,]  13  16  19  22
[2,]  14  17  20  23
[3,]  15  18  21  24
```

This array has three dimensions. Notice that, although the rows are given as the first dimension, the tables are filled column-wise. So, for arrays, R fills the columns, then the rows, and then the rest.

----
**Visualized difference between vector, matrix and array:**

{% include figure image_path="/assets/images/unit_images/u03/Array.png" caption="Note the structural difference between vectors, matrices and arrays." %}

A vector is one-dimensional, a matrix is two-dimensional and an array is more than two dimensional.

----

# Lists
A list is an object which can contain many different types of elements inside it like vectors, a matrix, functions and even another list inside it.
The list is created using the `list()` function. Unlike matrices list elements do not need equal length and same data types.

```r
# Create a list.
list1 <- list(c(2,5,3),21.3,sin)

# Print the list.
print(list1)
```

When we execute the above code, it produces the following result:

```r
[[1]]
[1] 2 5 3

[[2]]
[1] 21.3

[[3]]
function (x)  .Primitive("sin")
```
It prints one list with three elements. The first element  [[1]] is an vector containing values. The second element [[2]] is a value and the third [[3]] is a function.
Note, that in lists, that the selection of list element via single square brackets __[]__ preserves the list structure, which means that the result will still be a list if you extract a single element. while __[[]]__ returns the actual value stored within the selected element. Therefore, the choice between __[]__ and __[[]]__ depends on whether you want to work with the structure of the list or extract the values from it.

```r
list1[1]
[[1]]
[1] 2 5 3

list1[[1]]
[1] 2 5 3
```
As with our other non-atomic object type, the data frame, we can name the elements and address these elements with __“$”__

```r
names(list1) <- c("numbers","my.double","my.sin")

list1$numbers
[1] 2 5 3
```

----

# Factors
In R, a "factor" is a data structure used for fields that takes only predefined, finite number of values (categorical data). In such case, we know the possible values beforehand and these predefined, distinct values are called levels. Factors are more memory-efficient than storing categorical data as character vectors. This is because factors internally represent the data as integers and maintain a separate list of levels. They can have a specific order or hierarchy, which can be important when dealing with ordinal data. Factors with an order can be used in statistical analyses that consider the order of the levels. Using factors helps maintain data integrity by ensuring that values are limited to a predefined set of levels. This reduces the risk of errors and inconsistencies in data entry. 

In such case, we know the possible values beforehand and these predefined, distinct values are called levels.

A factor is created using the function `factor()`. Levels of a factor are inferred from the data if not provided.

```r
treecover <- factor(c("Spruce", "Spruce","Gap","Beech","Beech","Oak","Oak"))
treecover

[1] Spruce Spruce Gap Beech Beech Oak Oak
Levels: Beech Gap Oak Spruce
```

Here, we can see that factor *treecover* has seven elements and four levels. We can check if a object is a factor or not using `class()` function.

Similarly, levels of a factor can be checked using the `levels()` function. 

```r
class(treecover)
[1] "factor"

> levels(treecover)
[1] "Beech" "Gap" "Oak" "Spruce"
```
By default, the levels are assigned alphabetically. You can change this order by directly naming the levels in your preferred order while setting the factor:

```r
treecover <- factor(c("Spruce", "Spruce","Gap","Beech","Beech","Oak","Oak"), levels=c("Gap","Spruce","Fir","Beech","Oak"))
treecover

[1] Spruce Spruce Gap Beech Beech Oak Oak
Levels: Gap Spruce Fir Beech Oak 
```
When you define the factor levels explicitly, you are essentially specifying the allowed categories that this factor can have. This is a common practice, especially when you want to ensure that certain levels are present in the factor, or when you want to control the order of the levels.
However, if you do not explicitly specify all the possible levels when creating a factor, R will, by default, assign missing values (NA) to any values that do not match the predefined levels. This behavior ensures that any values outside the defined levels are recognized as missing data.

```r
treecover <- factor(c("Spruce", "Spruce","Gap","Beech","Beech","Oak","Oak","Birch"), levels=c("Gap","Spruce","Fir","Beech","Oak"))
treecover

[1] Spruce Spruce Gap Beech Beech Oak Oak <NA>
Levels: Gap Spruce Fir Beech Oak 
```
If you are working with ordinal data, set ordered=T:

```r
treecover <- factor(c("Spruce", "Spruce","Gap","Beech","Beech","Oak","Oak","Birch"), levels=c("Gap","Spruce","Fir","Beech","Oak"), ordered=T)
treecover

[1] Spruce Spruce Gap Beech Beech Oak Oak <NA>
Levels: Gap<Spruce<Fir<Beech<Oak 
```
-----


<!--
## Further reading
{% include figure image_path="/assets/images/unit_images/u03/grid.png" caption="A Matrix by [?](?)" %}

add some day
-->
