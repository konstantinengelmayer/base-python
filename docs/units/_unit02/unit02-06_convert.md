---
title: Converting Types of Data
header:
  image: /assets/images/unit_images/u03/header.png
  image_description: "neon data"
  caption: "Photo by [Franki Chamaki](https://unsplash.com/@franki?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) [from unsplash](https://unsplash.com/s/photos/data?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText)"
---
<!--more-->

> “Errors using inadequate data are much less than those using no data at all.” – Charles Babbage

---

In Python, data types are automatically assigned to variables, or the data type of a variable can be subsequently converted into another data type. To check the data type, the `type()` function is used. To check for a specific data type you can use the `isinstance()`-function. Conversion functions like int(), float(), and str() are used to change the data type.

Python has three numeric classes. The two most common are float (for floating-point numbers) and int (for integers). Python will automatically convert between numeric classes when needed, so it generally does not matter whether the number 3 is currently stored as an integer or a float. Most math is done using float precision, so that is often the default storage.

Sometimes you may want to specifically store a variable as an integer if you know that it will never be converted to a float (used as ID values or indexing) since integers require less storage space. But if they are going to be used in any math that will convert them to float, then it may be best to store them as floats from the beginning.

The table below gives an overview of the different data types in Python.

| Data Type  | check type                          | convert      |
|------------|-------------------------------------|--------------|
| integer    | `isinstance(x, int)`                | `int(x)`     |
| float      | `isinstance(x, float)`              | `float(x)`   |
| character  | `isinstance(x, str)`                | `str(x)`     |
| boolean    | `isinstance(x, bool)`               | `bool(x)`    |
| None       | `if x is None`                      | `x = None`   |
| NaN        | `math.isnan(x)` or `numpy.isnan(x)` | `x = np.nan` |


<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
div {
  margin-bottom: 15px;
  padding: 4px 12px;
}

.info {
  background-color: #e7f3fe;
  border-left: 6px solid #2196F3;
}

</style>
</head>
<body>
<div class="info">
  <p>*Info  <br>
  The function <code class="language-plaintext highlighter-rouge">numpy.isnan()</code> indicates which elements are NaN (missing or undefined).    <br><br>
  
  To set elements to NaN, you can use <code class="language-plaintext highlighter-rouge">numpy.nan</code>.  <br><br>

  While factors (categorical data) are a unique feature of R, Python uses the <code class="language-plaintext highlighter-rouge">pandas.Categorical</code> type to manage categorical data and maintain the integrity and order of those categories.
  </p>
</div>
</body>
</html>

<i>Example</i>
```python
value = 23.5

print(isinstance(value, float))
# Output: True

print(isinstance(value, str))
# Output: False
```

```python
colors = ["blue", "red", "red", "yellow"]
print(colors)
# Output: ['blue', 'red', 'red', 'yellow']

print(isinstance(colors, list))
# Output: True

# Convert to set to manage unique colors (similar to R's factor)
colors_set = set(colors)
print(colors_set)
# Output: {'blue', 'yellow', 'red'}
```
<!--more-->


<!--
## Further reading

add some day
-->
