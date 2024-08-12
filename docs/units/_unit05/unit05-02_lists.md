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

# Lists
Lists in Python are versatile objects that allow you to store multiple items in a single variable. They are one of the most commonly used data structures in Python due to their flexibility. A list can contain elements of different data types, including numbers, strings, functions, and even other lists. This makes lists ideal for grouping related items together and managing collections of data.

## What Are Lists Used For?
Lists are used for a wide variety of tasks in Python programming, such as:

- Storing Collections of Data: Lists can hold multiple items, making them useful for storing sequences of data like names, numbers, or other collections.
- Organizing Data: You can organize data into lists to perform operations like sorting, filtering, or iterating through items.
- Complex Data Structures: Lists can be nested within other lists, allowing you to create complex data structures like matrices or trees.
- Dynamic : Lists can grow or shrink in size, as you can add, remove, or modify elements at any time.

## Creating and Accessing Lists
A list is typically created using square brackets `[]`, with elements separated by commas. Here's an example:
```python
# Creating a list with multiple elements
# Create a list
list1 = [[2, 5, 3], 21.3, sum]

# Print the list
print(list1)

# Output: list1 = [[2, 5, 3], 21.3, sum]
```
In this example, `list1` contains a sublist `[2, 5, 3]`, a floating-point number `21.3`, and a reference to the built-in function `sum`.

You can access list elements using square brackets `[]`. Using single square brackets returns the element while preserving its structure as a list. To access the value inside, you again use `[]` to access the values

```python
# Accessing elements
print(list1[0])  # Output: [2, 5, 3]
print(list1[1])  # Output: 21.3
print(list1[2])  # Output: <built-in function sum>

# Accessing elements within a sublist
print(list1[0][1])  # Output: 5
```

Lists in Python are mutable, meaning you can change their contents after they are created. Here are some examples of modifying lists:

```python
# Modifying an element in the list
list1[1] = 42.0
print(list1)  # Output: [[2, 5, 3], 42.0, <built-in function sum>]

# Adding a new element to the list
list1.append("new item")
print(list1)  # Output: [[2, 5, 3], 42.0, <built-in function sum>, 'new item']

# Removing an element from the list
list1.remove(42.0)
print(list1)  # Output: [[2, 5, 3], <built-in function sum>, 'new item']
```