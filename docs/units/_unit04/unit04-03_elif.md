---
title: if and elif
header:
  image: /assets/images/unit_images/u07/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---

The `elif` statement in Python, short for "else if," allows you to check multiple conditions in sequence. It provides a way to handle more than just two possible outcomes (as with a simple if and else). With `elif`, you can check for additional conditions after the initial `if` statement, and only the first condition that evaluates to `True` will have its corresponding block of code executed.

## Example of elif Usage
Here’s a basic example:
```python
a = 10.0
b = 10.0

if a < b:
    print("a is smaller than b")
elif a == b:
    print("a equals b")
# Output:
# a equals b
```

In this example, the first `if` condition `a < b` is `False`, so Python checks the `elif` condition `a == b`, which is `True`, so the message "a equals b" is printed.

## Multiple `elif` Statements
You can include multiple `elif` statements to check for a variety of conditions:
```python
x = 25

if x < 10:
    print("x is less than 10")
elif x < 20:
    print("x is less than 20 but greater than or equal to 10")
elif x < 30:
    print("x is less than 30 but greater than or equal to 20")
# Output:
# x is less than 30 but greater than or equal to 20
```
In this example, Python evaluates each condition in sequence. Since `x` is 25, the first two conditions are `False`, but the third `elif` condition is `True`, so the corresponding message is printed.