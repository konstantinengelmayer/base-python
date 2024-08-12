---
title: Comparison Operators
header:
  image: /assets/images/unit_images/u07/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---
Comparison operators in Python allow you to compare values and determine their relationships. These operators are fundamental in making decisions and controlling the flow of your program.

| Operator  | Description                          | Example     |
|-----------|--------------------------------------|-------------|
| **Comparison Operators**                         ||
| `<`       | Test if x is smaller than y          | `x < y`     |
| `>`       | Test if x is greater than y          | `x > y`     |
| `==`      | Test if x is exactly equal to y      | `x == y`    |
| `>=`      | Test if x is greater than or equal to y | `x >= y` |
| `<=`      | Test if x is smaller than or equal to y | `x <= y` |
| `!=`      | Test if x is not equal to y          | `x != y`    |

## Less Than (<)
The < operator checks if the value on the left is less than the value on the right.
```python
x = 5
y = 10
result = x < y
print(result)
# Output: True
```

## Greater Than (>)
The > operator checks if the value on the left is greater than the value on the right.
```python
x = 10
y = 5
result = x > y
print(result)
# Output: True
```

## Equal To (==)
The == operator checks if the value on the left is exactly equal to the value on the right. This operator is commonly used in conditions to test equality.
```python
x = 10
y = 10
result = x == y
print(result)
# Output: True
```

## Greater Than or Equal To (>=)
The >= operator checks if the value on the left is greater than or equal to the value on the right.
```python
x = 10
y = 10
result = x >= y
print(result)
# Output: True
```

## Less Than or Equal To (<=)
The <= operator checks if the value on the left is less than or equal to the value on the right.
```python
x = 5
y = 10
result = x <= y
print(result)
# Output: True
```

## Not Equal To (!=)
The != operator checks if the value on the left is not equal to the value on the right. This is useful for testing inequality.
```python
x = 10
y = 5
result = x != y
print(result)
# Output: True
```