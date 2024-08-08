---
title: "Numbers (Integers, Floats)"
toc: true
header:
  image: /assets/images/unit_images/u03/header.png
  image_description: "neon data"
  caption: "Photo by [Franki Chamaki](https://unsplash.com/@franki?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) [from unsplash](https://unsplash.com/s/photos/data?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText)"
---

<!--more-->

### Integers
Integers are whole nubers without a decimal point. They can be positive, negative, or zero. 

### Floats
Floats (floating-point numbers) are numbers that have a decimal point. They also can be positive, negative, or zero. 

### Performing Arithmetic Operations
As shown before Python can be used as a calculator to perform arithmetic operations. You can also perfom operations with integers and floats and once. The results wil be a float.

```python
sum = 5 + 4.2
print(sum)
# Output: 9.2
```

### Built-in Functions for Numeric Data
Python provides several built-in functions to manipulate numeric data.
The `type()` function returns the data type of a variable.

```python
# Check types
type(5)
# Output: <class 'int'>

type(3.14)
# Output: <class 'float'>
```

The `int()` function converts a float to an integer by truncating the decimal part. 
```python
# Convert float to integer
int_value = int(3.99)
# Output: 3
```

The `float()` function converts an integer to a float.
```python
# Convert integer to float
float_value = float(7)
# Output: 7.0
```

However python handles the conversion between int and float automatic and you rarely need to handle it yourself.