---
title: Work Environment
toc: TRUE
toc_float: TRUE
header:
  image: /assets/images/unit_images/u05/header.png
  image_description: "work environment"
  caption: "Photo by [Lukas Goumbik](https://pixabay.com/de/users/Goumbik-3752482/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=2055522) from [Pixabay](https://pixabay.com)"
---
<!--more-->

> “Data is the new oil.” — Clive Humby

---

# What is a workspace?**
> “A workspace is (often) a file or directory that allows a user to gather various source code files and resources and work with them as a cohesive unit. Often these files and resources represent the complete state of an integrated development environment (IDE) at a given time, a snapshot. Workspaces are very helpful in cases of complex projects when maintenance can be challenging.” — [Wikipedia](https://en.wikipedia.org/wiki/Workspace)

Let's create a directory for this course if you don't already have one. Create a folder somewhere on your computer with a logical name (e.g., base_python_course).

Next, create subfolders to organize your work. Useful subfolders might include:

- `data`: For storing datasets
  - `raw_data`: For raw datasets
  - `output_data`: For processed data
- `scripts`: For storing your code
- `documents`: For documentation and notes
  - `figures`: For figures and maps

The specific structure you choose is up to you, but ensure each folder has a logical name and makes sense in the context of your project.
Now let's add this folder to our VS Code workspace:
{% include figure image_path="/assets/images/unit_images/u05/open_folder.PNG" caption="" %}

If you opened the folder the **1. Explorer**  should be visible on the left. If you then open a script it wil be displayed in the middle of your screen (**2. Scripts**). In Jupyter Notebook it is possible to look at the variables you created in your script and which are saved in your **3. Environment**. Just click on `Variables` at the top of your script, marked by the arrow. If the `Variables`-Button is not visible it is because there a no saved variables in you environment.
{% include figure image_path="/assets/images/unit_images/u05/workspace.jpg" caption="" %}

## Understanding the directory structures

In Python, you need to explicitly instruct the program on how to access a file from the current working directory because a data file may reside in a different directory than the script calling it.

Consider an example where the user Geomoer has a project folder called `A_GREAT_PROJECT`, which contains ./data and ./scripts folders. If they open a Python script with the following line and run it:

```python
import pandas as pd
data = pd.read_csv('data.csv')

# Output:
# FileNotFoundError: [Errno 2] No such file or directory: 'data.csv'
```

But python returns an error message, which states that the file data.csv cannot be found. This is because the session’s working directory is probably set to a directory other than the `C:/geomoer/A_GREAT_PROJECT/data/raw` directory which contains the data file.

An python session’s working directory can be verified by using to os library typing the following command:
```python
import os

print(os.getcwd())
```

The working directory is used to instruct python where to look for a file (or where to create one) if the directory path is not explicitly defined. So in the example above, user Geomoer is asking python to open the file data.csv without explicitly telling python in which directory to look so python is defaulting to the current working directory which is `C:/geomoer/A_GREAT_PROJECT/scripts` which does not contain the csv file.

There are two options to resolve this problem.

The first is to set the working directory to the folder that contains the data.csv file using the `os.chdir()` function.
```python
os.chdir("C:/geomoer/A_GREAT_PROJECT/data/raw")
data = pd.read_csv("data.csv")
```
The second is to modify the read.csv call by specifying the path to the data.csv file.

```python
data = pd.read_csv("C:/geomoer/A_GREAT_PROJECT/data/raw/data.csv")
```
<html>
<body>
<div class="info">
  <p><strong>Hint:</strong> Pay attention to the quotation marks.</p>
</div>
</body>
</html>


### Relative and absolute paths

However, this approach makes it difficult to share the project folder with someone else who may choose to place it under a different folder such as `D:/Uni/R/Test/A_GREAT_PROJECT/`.

In such a scenario, the user would need to modify every Python script that references the directory `C:/geomoer/A_GREAT_PROJECT/`. A better solution is to specify the location of the data folder __relative__ to the location of the Analysis folder such as,

```python
data = pd.read_csv("../data/raw/data.csv")
```
The two dots **..** tells Python to move up the directory hierarchy relative to the current working directory. So in our working example, `../` tells Python to move out of the `scripts/` folder and up into the `A_GRREAT_PROJECT/` folder. The relative path `../data/raw/data.csv` tells Python to move out of the `scripts/` directory and over into the `data/raw/` directory before attempting to read the contents of the `data.csv` data file.

Using relative paths makes your project folder independent of the full directory structure in which it resides thus facilitating the reproducibility of your work on a different computer or root directory environment.

**Absolute and relative paths**
An absolute (or full) path points to the same location in a file system, regardless of the current working directory. To do that, it must include the root directory. For example: `C:/geomoer/A_GREAT_PROJECT/data/raw/data.csv`

By contrast, a relative path starts from some given working directory `(C:/geomoer/A_GREAT_PROJECT/)`, avoiding the need to provide the __full__ absolute path. For example: `../data/raw/data.csv`



<html>
<body>
<div class="info">
  <p><strong>Important Note to Windows Users:</strong><br>
  Python gets confused if you use a path in your code like:<br><br>

  c:\mydocuments\myfile.txt<br><br>

  This is because Python sees "\" as an escape character. Instead, use:<br><br>

  c:\\my documents\\myfile.txt<br><br>

  or<br><br>

  c:/mydocuments/myfile.txt<br><br>

  Either will work. We use the second convention throughout this platform.
  </p>
</div>
</body>
</html>


<!--
## Further reading

add some day
-->
