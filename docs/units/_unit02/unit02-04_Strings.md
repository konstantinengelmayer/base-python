---
title: "Strings"
toc: true
header:
  image: /assets/images/unit_images/u03/header.png
  image_description: "neon data"
  caption: "Photo by [Franki Chamaki](https://unsplash.com/@franki?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) [from unsplash](https://unsplash.com/s/photos/data?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText)"
---

<!--more-->

## What are Strings
Strings are sequences of characters enclosed in quotes. They can be created using single quotes ('), double quotes ("), or triple quotes (''' or """) for strings that span multiple lines.
```python
# Examples of strings
single_quote_string = 'Hello, World!'
double_quote_string = "Hello, World!"
triple_quote_string = """This is a 
multi-line string."""
```

## Basis String Operations

#### Indexing
Strings are indexed, starting at 0. A sequence of characters is stored in a string data type. So you can access each character of a string when using `[]`.
```python
my_string = "Hello"
print(my_string[0]) # Output: H
print(my_string[1]) # Output: e
print(my_string[4]) # Output: o
```

#### Concatenation (`+`)
Concatenation is the process of joining two or more strings together using the + operator.
```python
greeting = "Hello"
name = "Alice"
full_greeting = greeting + ", " + name + "!"
print(full_greeting)
# Output: "Hello, Alice!"
```

#### Repetition (`*`)
Repetition is the process of repeating a string multiple times using the `*` operator.
```python
repeat_greeting = "Hello! " * 3
print(repeat_greeting)
# Output: "Hello! Hello! Hello! "
```

#### Slicing (`:`)
Slicing allows you to extract a portion of a string using indices. The slice operator `:` is used to specify the start and end indices of the substring.
```python
sample_string = "Hello, World!"
substring = sample_string[0:5]
print(substring)
# Output: "Hello"
```

## Built-in String Functions
Python provides several built-in methods for string manipulation.

The `print()` function outputs strings (or other data types) to the console. We have used that function before.
```python
# Print a string
print("Hello, World!")
# Output: Hello, World!

# Print a string variable
message = "Hello, Python!"
print(message)
# Output: Hello, Python!
```

The `len()` function returns the length of a string.

```python
length = len("Hello, World!")
print(length)
# Output: 13
```

The `str()` function converts other data types to strings.
```python
number = 42
number_string = str(number)
print(number_string)
# Output: '42'
```

## Built-in String Methods
The `replace()` method replaces occurrences of a substring with another substring.
```python
original_string = "Hello, World!"
new_string = original_string.replace("World", "Python")
print(new_string)
# Output: "Hello, Python!"
```

The `find()` method returns the lowest index of the first occurrence of a substring, while `rfind()` returns the highest index of the last occurrence.
```python
# Find first occurrence
text = "Hello, World! Hello, Python!"
index_hello = text.find("Hello")
# Output: 0

# Find last occurrence
index_hello_last = text.rfind("Hello")
# Output: 13
```

The `count()` method returns the number of occurrences of a substring in a string.
```python
text = "Hello, World! Hello, Python!"
count_hello = text.count("Hello")
# Output: 2
```

The `split()` method splits a string into a list of substrings based on a delimiter.
```python
# Splits string at all spaces
sentence = "Hello, World! How are you?"
words = sentence.split(" ")
# Output: ['Hello,', 'World!', 'How', 'are', 'you?']
```

The `splitlines()` method splits a string at line breaks and returns a list of lines.
```python
# Split string into lines
multiline_string = """This is line one.
This is line two.
This is line three."""
lines = multiline_string.splitlines()
# Output: ['This is line one.', 'This is line two.', 'This is line three.']

```