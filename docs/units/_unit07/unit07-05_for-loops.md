---
title: For-loops
toc: TRUE
toc_float: TRUE
header:
  image: /assets/images/unit_images/u07/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---

For-loops are the mother of all repeating structures which enable the execution of certain code blocks for multiple times. For-loops are useful if the number of necessary repetitions is known at the starting time of the loop (which is not necessarily the starting time of the program!).

In for loops, the number of repeated executions is given at the start time either by a variable which is defined during the runtime of the previous code or by a constant supplied by the programmer. Imaging that we know already how many times the loop has to be repeated, one can implement it simply as:

```python
for i in range(7, 11):
    print(i)
# Output:
# 7
# 8
# 9
# 10

# Remember that the last number of a range is excluded
```
Note that the variable i which controls the for loop must not be changed within the loop.

Of course, you can nest for loops:

```python
for a in range(7, 11):
    print(f"Outer loop value of a: {i}")  # f-string with {i} embedded
    if i < 10:
        lower_border = i + 1
    else:
        lower_border = i
    for c in range(10, lower_border - 1, -1): # range(start, stop, step size)
        print(f"   Inner loop value of c: {j}")  # f-string with {j} embedded
# Outer loop value of a: 7
#    Inner loop value of c: 10
#    Inner loop value of c: 9
#    Inner loop value of c: 8
# Outer loop value of a: 8
#    Inner loop value of c: 10
#    Inner loop value of c: 9
# Outer loop value of a: 9
#    Inner loop value of c: 10
# Outer loop value of a: 10
#    Inner loop value of c: 10
```

The loop might look complicated but the reason for that is just the if-else statement. It is necessary since the second loop must run from `c` to the integer value just larger than `a` (i.e. 8, 9, 10). Therefore, `a` must be increased by 1 if it is smaller than 10 but stay 10 if it equals 10.

Instead of defining the number of repetitions in the for loop statement, one can also use any vector variable. The number of iterations will always be equal to the length of the vector. This is not surprising, since the `range` function used so far also simply returns an iterable, e.g.:

```r
t = range(7, 11)
print(t)
# Output: 
# 7  8  9 10
```

## DIY loops - some tipps

Sometimes it can be a little overwhelming to write a loop from top to bottom. That's why it makes sense to tackle the whole thing piece by piece. The following approach might be helpful:

1. Start by setting up an empty for loop, establishing the structure for your iterative process. This initial step helps maintain proper text indentation and structure in your code.

2. Take one piece of your data and define it as your data source.

3. Write down all the operations you want to perform within the loop.

4. Identify and handle replaceable elements within your loop. These are parts of your code that may change during each iteration. Use variables or placeholders to represent these elements, enhancing code flexibility and readability.

5. Think about how you want to save the output of each iteration. Create a result container, such as a list or DataFrame, outside the loop, and store the results there.

6. Consider using vectorized operations when possible to improve loop efficiency and reduce code complexity.

7. Debug and test your loop incrementally, checking for errors and unexpected behavior after each iteration. Depending on the complexity of the data, the loop may not be complete. Missing data, for example, often leads to an index out of range error. To eliminate these errors bit by bit, you can use the print(i) command to specify the point at which the loop stops, and continue to process the data or add conditions accordingly.

{% include figure image_path="/assets/data/data/for_loop2.gif" caption="Animation of the plot process" %}


## Test what you've learned so far!

<iframe src="https://geomoer.github.io/moer-h5p-content/h5p-standalone-1.3.x/demo/base-r-unit07-forloops.html" width="1090" height="600" frameborder="0" allowfullscreen="allowfullscreen" allow="geolocation *; microphone *; camera *; midi *; encrypted-media *"> </iframe><script src="https://h5p.org/sites/all/modules/h5p/library/js/h5p-resizer.js" charset="UTF-8"></script> 






