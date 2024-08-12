---
title: Looping Trough Lists and Tuples
toc: TRUE
toc_float: TRUE
header:
  image: /assets/images/unit_images/u07/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---

For-loops are extremely useful when working with lists and tuples, as they allow you to iterate over each element and perform operations on them. Unlike range-based loops, iterating directly over lists or tuples simplifies code and avoids common errors, such as index out of bounds.

## Looping Through a List
Here’s a basic example of looping through a list:
```python
letters = ["A", "B", "C", "D"]
for element in letters:
    print(element)
# Output:
# A
# B
# C
# D
```
In this example, the loop iterates over each element in the list `letters`, printing each letter one by one.

You can modify elements of a list directly within a loop. Here’s how to add an "x" to each entry in the list letters:
```python
for i in range(len(letters)):
    letters[i] = letters[i] + "x"
print(letters)
# Output:
# ['Ax', 'Bx', 'Cx', 'Dx']
```

If you need to create a new list based on the elements of an existing list, you can initialize an empty list and append to it within the loop:
```python
a = ["A", "B", "C", "A", "B", "A", "A"]
test = []  # this is an empty list
for i in range(len(a)):
    test.append(a[i].lower())

print(test)
# Output:
# ['a', 'b', 'c', 'a', 'b', 'a', 'a']
```

## Looping Through a Tuple
Tuples are similar to lists but are immutable, meaning their elements cannot be changed after creation. You can loop through tuples just like lists:
```python
colors = ("red", "green", "blue")
for color in colors:
    print(color)
# Output:
# red
# green
# blue
```