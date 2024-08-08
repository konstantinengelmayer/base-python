---
title: "First Steps in Python"
toc: TRUE
toc_float: TRUE
header:
  image: /assets/images/unit_images/u01/header.png
  image_description: "confused"
  caption: "Image by [slon_pics](https://pixabay.com/de/users/www_slon_pics-5203613/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=2261021) [from pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=2261021)"
---
*Making your first steps in R with simple arithmetic operations.*

<!--more-->

## #Hashtag and Run!

Let's open our first Jupyter Notebook. Press `Ctrl+Shift+P` to open the command palette and search for `>Create: New Jupyter Notebook`. Here VS Code automatically creates the first code block for you. Try to enter this line of code:
```python
print('Welcome to Python)
```
To run the block of code you can press `Shift+Enter`. Now VS Code will ask you for your Python interpreter. Here you have to chose your miniconda virtual environment. Then you can run your code. 

You can also comment your code to make it easier to understand for other and yourself. Python treats the hashtag character, **#**, in a special way. It will not compile anything that follows a # on a line. This makes hashtags very useful for adding comments and annotations to your code. You will be able to read the comments, but your computer will pass over them.

```python
# This is a comment. Comments are very helpful
# when you want to describe what's going on in your code.
# Use them often!
This is not a comment anymore. Be careful.

print("Welcome to R")
```

{% include figure image_path="/assets/images/unit_images/u01/VS_code_first_steps.PNG" caption="VS Code Overview" %}

As you see, in VS code you have many button to click on. Let's o over the most important ones. The `+Code` button create a new code chunk where you can insert new code. The `+Markdown` button create a markdown chunk. Markdown is a lightweight markup language used to format text with simple syntax for styling, such as headers, lists, and emphasis. With markdown you can explain and structure you code in more detail. This is why Jupyter Notebook is such a convenient tool, because you can run code and explain in really detailed in one file combined.

In Markdown, headers are created using the `#` symbol. The number of # symbols indicates the level of the header (e.g., `#` for level 1, `##` for level 2). Normal text is simply written without any special formatting symbols.

{% include figure image_path="/assets/images/unit_images/u01/VS_code_markdown.PNG" caption="VS Code Markdown Cell" %}

When clicking the little checkmark marked with the orange arrow the markdown code will be change to text format.