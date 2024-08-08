---
title: "Boolean Values"
toc: true
header:
  image: /assets/images/unit_images/u03/header.png
  image_description: "neon data"
  caption: "Photo by [Franki Chamaki](https://unsplash.com/@franki?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) [from unsplash](https://unsplash.com/s/photos/data?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText)"
---

<!--more-->

## What are Booleans?
Booleans are a data type that can hold one of two values: True or False. They are used to represent truth values and are essential for making decisions in your programs.
```python
is_true = True
is_false = False
```

## Boolean Expressions
Boolean expressions are expressions that evaluate to either True or False. They are commonly used in conditional statements and loops. There are two kind of operators. Relational and Logical Operators.

| **Relational Operators**                         ||
| <         | Test if x is smaller than y          | `x < y`     |
| >         | Test if x is greater than y          | `x > y`     |
| ==        | Test if x is exactly equal to y      | `x == y`    |
| >=        | Test if x is greater than or equal to y | `x >= y` |
| <=        | Test if x is smaller than or equal to y | `x <= y` |
| !=        | Test if x is not equal to y          | `x != y`    |
| **Logical Operators**                            ||
| not       | Logical NOT                          | `not x`     |
| &         | Element-wise logical AND             | `x & y`     |
| and       | Logical AND                          | `x and y`   |
| \|        | Element-wise logical OR              | `x | y`     |
| or        | Logical OR                           | `x or y`    |

#### Comparison Operators
Comparison operators are used to compare values. The result of a comparison is a Boolean value.

```python
a = 10
b = 5

# Greater than
print(a > b)
# Output: True

# Less than
print(a < b)
# Output: False

# Equal to
print(a == b)
# Output: False

# Not equal to
print(a != b)
# Output: True

# Greater than or equal to
print(a >= b)
# Output: True

# Less than or equal to
print(a <= b)
# Output: False
```

#### Logical Operators
Logical operators are used to combine Boolean expressions.
```python
x = True
y = False

# AND operator
result = x and y
# Output: False --> because not both are true (would be true if x and y are true)

# OR operator
result = x or y
# Output: True  --> gets true if one of both variables are true

# NOT operator
result = not x
# Output: False --> 'not' turns around true and false
```

