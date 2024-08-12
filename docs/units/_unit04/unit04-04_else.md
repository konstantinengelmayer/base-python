---
title: if, elif and else
header:
  image: /assets/images/unit_images/u07/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---

The `else` statement in Python is used to define a block of code that will execute `if` none of the preceding `if` or `elif` conditions are `True`. The `else` statement provides a fallback mechanism in your conditional logic, ensuring that your program can handle cases that don’t match any of your specified conditions.

## How else Works
An `else` statement is typically placed at the end of an if-elif chain. When Python encounters an if-elif-else structure:

- It first evaluates the `if` condition. If `True`, the code inside the `if` block is executed, and Python skips the rest of the conditions.
- If the `if` condition is `False`, Python moves on to evaluate the `elif` conditions in order, when there are any.
- If none of the `if` or `elif` conditions are `True`, the code inside the else block is executed.

## Example of else Usage
Here’s a basic example:
```python
a = 15.0

if a > 20 :
    print("a is larger than 20")
elif a > 15 :
    print("a is larger than 15")
else:
    print("a is smaller than 15)
# Output:
# a is larger than b
```

`else` can also directly follow an `if`-statement without `elif`.
```python
a = 15.0
b = 20.0

if a < b:
    print("a is smaller than b")
else:
    print("a is not smaller than b")
# Output:
# a is smaller than b
```