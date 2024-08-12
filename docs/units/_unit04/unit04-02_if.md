---
title: if Statement
header:
  image: /assets/images/unit_images/u07/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---

In Python, `if` statements are used to control the flow of a program by executing certain blocks of code only when specific conditions are met. The basic form of an `if` statement checks a condition and executes the following indented block of code `if` the condition is True

## Basic `if` Statement
Here’s an example of a simple `if` statement:
```python
a = 5.0
b = 10.0
if a < b:
    print("a is smaller than b")
# Output:
# a is smaller than b
```

## Using logical operators in `if` Statements
You can also use more complex boolean expressions within if statements to make more precise decisions:
```python
c = 5
if a < b and a == c:
print("a is smaller than b and equal to c")
# Output:
# a is smaller than b and equal to c
```

## Negating Conditions with `not`
The `not` operator can be used to check if a condition is `False`:
```python
if not a < b:
    print("a is not smaller than b")
# Output:
# a is not smaller than b
```
If you would exclude the `not`, the condition would be `False` and you wound't get an output.