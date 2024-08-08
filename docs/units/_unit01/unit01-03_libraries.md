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

1. **Efficiency**: Libraries save time by providing pre-built functions and modules, allowing you to focus on the unique aspects of your project**.
2. **Reliability**: Libraries are often tested and optimized by a large community of developers, ensuring robust and efficient code.
3. **Consistency**: Using libraries promotes consistency in your codebase, making it easier to read, maintain, and collaborate with others.
4. **Functionality**: Libraries offer advanced features and capabilities that would be complex and time-consuming to implement on your own.

## Create a Virtual Environment with Miniconda

A virtual environment is an isolated environment that allows you to manage libraries for different projects separately. This is crucial for several reasons:

1. **Dependency Management**: Different projects might require different versions of libraries. Virtual environments allow you to maintain these dependencies without conflicts.
2. **Project Isolation**: Each virtual environment is independent, ensuring that changes in one project do not affect another.
3. **Reproducibility**: Virtual environments help in replicating the development environment, making it easier to share and collaborate on projects.
4. **Cleaner System**: By using virtual environments, you avoid installing packages globally, keeping your base system clean and organized.

Creating a virtual environment ensures that your projects remain manageable, reproducible, and free from dependency conflicts.

Now let's create a virtual environment with miniconda:

1. Open your miniconda powershell.
2. Create a new virtual environment by running the following command:
   ```sh
   conda create -n myenv python=3.9
   ```
   Replace `myenv` with the name you want for your environment and `3.9` with the desired Python version.
3. Activate you new virtual environment calling its name and download necessary libraries for the course:
   ```sh
   conda activate myenv
   ```
4. Now you can install th libraries needed inside that virtual environment:
   ```sh
   conda install numpy
   conda install pandas
   conda install matplotlib
   ```
  These libraries are needed for numerical computations and array handling (`NumPy`), data manipulation and analysis (`pandas`), and creating visualizations (`Matplotlib`).
{% include figure image_path="/assets/images/unit_images/u01/miniConda.PNG" %}