---
title: Loops
toc: TRUE
toc_float: TRUE
header:
  image: /assets/images/unit_images/u07/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---
In programming, loops are fundamental constructs that allow you to repeat a block of code multiple times without having to write it out repeatedly. They are essential for automating repetitive tasks, iterating over data structures like lists or arrays, and performing operations until a specific condition is met.

Loops save time, reduce errors, and make your code more efficient and readable. In Python, there are two primary types of loops: the for loop and the while loop.

## Why Use Loops?
- Efficiency: Loops reduce the need for redundant code, allowing you to perform repetitive tasks more efficiently.
- Automation: They automate tasks by repeating actions until a certain condition is met.

### For-loop
Useful if your computation needs the same sequential workflow for different variables or subsets.
```
# Pseudocode
for <iteration variable> in <control vector>:
    # do something using the iteration variable
```

### While-loop
Useful if your computation needs the same sequential workflow for a variable or subsets but you only know how often it is needed when the loop is already running.

```
# Pseudocode
while <some logical expression with iteration variable>:
    # do something using iteration variable and update it
```
------

## What loop to choose?

{% include figure image_path="/assets/images/unit_images/u07/which-loop-to-choose.jpg" alt="Flow chart showing a decision tree which helps to choose the right loop." %}

One rule for choosing between a while- and a for-loop is that __while-loops__ are used when the number of iterations is __unknown__ and __for-loops__ are used when the number is __known__.

Let’s go through a few examples of each:

* Use a for-loop to iterate over an array.
* Use a for-loop when you know the loop should execute *n* times.
* Use a while-loop for reading a file into a variable.
* Use a while-loop when asking for user input.
* Use a while-loop when the increment value is nonstandard.

## Importance of Indentation in Python
Indentation is crucial in Python because it determines the structure and flow of the code. Unlike many other programming languages that use braces or keywords to define code blocks, Python uses indentation to group statements.

How Indentation Works:
1. Each level of indentation should be consistent (typically 4 spaces).
2. All statements within the same block should be indented to the same level (e.g things that should happen if and if-statement is True).
3. The end of the indentation signifies the end of the code block.
