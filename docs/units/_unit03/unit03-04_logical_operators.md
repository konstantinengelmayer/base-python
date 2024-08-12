---
title: Logical Operators
header:
  image: /assets/images/unit_images/u07/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---
Logical operators in Python are used to combine multiple conditions and perform logical operations. These operators are fundamental for decision-making in your code, allowing you to control code based on multiple conditions.

| Operator  | Description                          | Example     |
|-----------|--------------------------------------|-------------|
| **Logical Operators**                            ||
| `not`     | Logical NOT                          | `not x`     |
| `&`       | Element-wise logical AND             | `x & y`     |
| `and`     | Logical AND                          | `x and y`   |
| `|`       | Element-wise logical OR              | `x | y`     |
| `or`      | Logical OR                           | `x or y`    |


## Logical NOT (not)
The not operator is a unary operator that inverts the Boolean value of its operand. If the operand is True, not makes it False, and vice versa.
```python
x = True
result = not x
print(result)
# Output: False
```

## Logical AND (and)
The and operator returns True if both operands are True; otherwise, it returns False. This operator is commonly used to ensure that multiple conditions are met before executing a block of code.
```python
x = True
y = False
result = x and y
print(result)
# Output: False
```

## Logical OR (or)
The or operator returns True if at least one of the operands is True. It is used when you want to execute code if one or more conditions are met.
```python
x = True
y = False
result = x or y
print(result)
# Output: True
```

## Element-wise Logical AND (&)
The & operator performs element-wise logical AND operations, typically used with arrays or lists. This operator is more commonly used in data science and array manipulations with libraries like NumPy.
```python
import numpy as np

array1 = np.array([True, False, True])
array2 = np.array([False, False, True])

result = array1 & array2
print(result)
# Output: [False False  True]
```

## Element-wise Logical OR (|)
The | operator performs element-wise logical OR operations, similar to the & operator but returns True if at least one of the corresponding elements is True.
```python
import numpy as np

array1 = np.array([True, False, True])
array2 = np.array([False, False, True])

result = array1 | array2
print(result)
# Output: [ True False  True]
```