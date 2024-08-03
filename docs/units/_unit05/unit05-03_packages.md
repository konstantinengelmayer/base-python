---
title: Installing Libraries in Python
toc: TRUE
toc_float: TRUE
collapsed: TRUE
smooth_scroll: TRUE
header:
  image: /assets/images/unit_images/u05/header.png
  image_description: "work environment"
  caption: "Photo by [Lukas Goumbik](https://pixabay.com/de/users/Goumbik-3752482/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=2055522) from [Pixabay](https://pixabay.com)"
---

# What are Libraries?
In programming, libraries are collections of pre-written code that provide reusable functions, classes, and methods to perform common tasks. Libraries can significantly simplify your development process by allowing you to leverage existing solutions rather than writing code from scratch. They cover a wide range of functionalities such as data manipulation, machine learning, web development, and more.

## Why Do We Need Libraries?
Libraries are essential for several reasons:

1. Efficiency: Libraries save time by providing pre-built functions and modules, allowing you to focus on the unique aspects of your project.
2. Reliability: Libraries are often tested and optimized by a large community of developers, ensuring robust and efficient code.
3. Consistency: Using libraries promotes consistency in your codebase, making it easier to read, maintain, and collaborate with others.
4. Functionality: Libraries offer advanced features and capabilities that would be complex and time-consuming to implement on your own.

## Libraries You've Used
In this course, you have already downloaded and used libraries such as `pandas` and `numpy` for data manipulation and numerical operations. These libraries were installed at the beginning of the course to help you efficiently manage and analyze data.

In this tutorial, we will learn how to download and install new libraries into your Python environment using Miniconda, using the `matplotlib` library as an example, which we will need later in this course.

`Matplotlib` is a comprehensive library for creating static, animated, and interactive visualizations in Python. It is highly versatile and can be used for a variety of plotting tasks.

## Steps
1. Open your miniconda prompt. You can do this by searching for "miniconda" in your system's search bar.

2. Open your virtual python environment with `conda activate` and the name of your environment.
```sh
conda activate example_env
```
Incase you forgot the name of your python environment you can use following code to give you a list of all available miniconda environments on your computer:
```sh
conda env list
# example Output:
# base                  *  C:\Users\geomer\miniconda3
# example_env              C:\Users\geomer\miniconda3\envs\example_env
```

3. Now that you activated your environment you can run the code for installing `matplotlib`.
```sh
conda install matplotlib
```

Since your library is installed now, you can import it to your Python script like this:
```python
import matplotlib.pyplot as plt
```
