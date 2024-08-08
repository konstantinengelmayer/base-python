---
title: Creating graphs
toc: true
toc_float: true
header:
  image: /assets/images/unit_images/u09/header.png
  image_description: "statistics"
  caption: "Photo by [Gerd Altmann](https://pixabay.com/de/users/geralt-9301/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4705451) [from Pixabay](https://pixabay.com/)"
---

> “No design works unless it embodies ideas that are held common by the people for whom the object is intended.” - Adrian Forty
<!--more-->


Using Python with libraries like `matplotlib` offers many advantages not only in data analysis but also in creating scientific graphs. Python makes it possible:
- to produce high-quality graphs that are also suitable for professional printing.
- to create graphics completely in Python syntax and thus make them reproducible.
- to flexibly combine different types of graphics or develop your own forms of presentation.
- to easily create uniformly designed graphics.

Do not wait until the very final analysis stage to produce some publication quality graphics but produce fast (not necessarily nice) visualizations all the way through your data analysis. Otherwise you will not utilize the best neural network infrastructure you have available: your brain and it's ability to identify patterns.

## Basic plots in R

The `plot()` function in `matplotlib` is the universal function for generating scatter plots and line plots from data arrays. The plot can be optionally adjusted with various parameters:

| Parameter   | Description | Example |
|-------------|-------------|---------|
| linestyle   | sets the line style: <br> "-" -> solid line <br> "--" -> dashed line <br> "-." -> dash-dot line <br> ":" -> dotted line <br> " " -> no line | linestyle="--" |
| marker      | sets the marker style: <br> "o" -> circle <br> "s" -> square <br> "D" -> diamond <br> "^" -> triangle_up <br> " " -> no marker | marker="o" |
| color       | sets the color of lines, dots, bars, etc. | color="blue" <br> color="#112233" (RGB value) |
| title       | sets the main title of the plot | title="Population growth (annual %)" |
| xlabel      | sets the label of the x-axis | xlabel="Years 2000 to 2020" |
| ylabel      | sets the label of the y-axis | ylabel="Population Growth in %" |
| linewidth   | sets the line width | linewidth=2 |
| markersize  | sets the size of the markers | markersize=5 |
| xlim        | sets the start and end values of the X-axis scale | xlim=(0, 20) |
| ylim        | sets the start and end values of the y-axis scale | ylim=(100, 160) |



## Let's have some fun
The following is an introduction for producing simple graphs.

Define 2 lists for two different datasets:
```python
sport_cars = [1, 2, 4, 2, 6, 7, 10]
family_cars = [3, 6, 6, 8, 6, 5, 2]
```

Then calculate the range from 0 to max value of sport cars and family cars:
```python
max_range = [0, max(max(sport_cars), max(family_cars))]
```

We graph the cars using the y axis that ranges from 0 to max value in sports or family cars and turning off axes and annotations (axis labels) so we can specify them ourself.
```python
import matplotlib.pyplot as plt

plt.plot(sport_cars, 'o-', color='blue', ylim=max_range, label='Sport', markersize=5)
plt.xticks(ticks=range(len(sport_cars)), labels=["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"])
plt.yticks(ticks=range(0, max_range[1]+1, 4))
plt.box(on=True)
```

{% include figure image_path="/assets/data/data/plot1.png" caption="Print of Code chunk above" %}

Make x axis using Mon-Fri labels
```
axis(1, at=1:7, lab=c("Mon","Tue","Wed","Thu","Fri","Sat","Sun"))
```
{% include figure image_path="/assets/data/data/plot2.png" caption="Print of Code chunk above" %}

Make y axis with horizontal labels that display ticks at every 4 marks. 4*0:g_range[2] is equivalent to c(0,4,8,12).
```
axis(2, las=1, at=4*0:max_range[2])
```
{% include figure image_path="/assets/data/data/plot3.png" caption="Print of Code chunk above" %}

Create box around plot
```
box()
```
{% include figure image_path="/assets/data/data/plot4.png" caption="Print of Code chunk above" %}

Graph trucks with red dashed line and square points
```
lines(family_cars, type="o", pch=22, lty=2, col="red")
```
{% include figure image_path="/assets/data/data/plot5.png" caption="Print of Code chunk above" %}

Create a title with a red, bold/italic font
```
title(main="Car Types on Streets", col.main="red", font.main=4)
```
{% include figure image_path="/assets/data/data/plot6.png" caption="Print of Code chunk above" %}

Label the x and y axes with dark green text
```
title(xlab="Days", col.lab=rgb(0,0.5,0))
title(ylab="Total", col.lab=rgb(0,0.5,0))
```
{% include figure image_path="/assets/data/data/plot7.png" caption="Print of Code chunk above" %}

Create a legend at (1, g_range[2]) that is slightly smaller (cex) and uses the same line colors and points used by  the actual plots
```
legend(1, max_range[2], c("Sport","Family"), cex=0.8,
       col=c("blue","red"), pch=21:22, lty=1:2);
```

{% include figure image_path="/assets/data/data/plot8.png" caption="Print of Code chunk above" %}

In total this is the code and the output in the plot-window will look like this with each line:
```
sport_cars <- c(1, 2, 4, 2, 6, 7, 10)
family_cars <- c(3, 6, 6, 8, 6, 5, 2)
max_range <- range(0, sport_cars, family_cars)
plot(sport_cars, type="o", col="blue", ylim=max_range,
     axes=FALSE, ann=FALSE)
axis(1, at=1:7, lab=c("Mon","Tue","Wed","Thu","Fri","Sat","Sun"))
axis(2, las=1, at=4*0:max_range[2])
box()
lines(family_cars, type="o", pch=22, lty=2, col="red")
title(main="Car Types on Streets", col.main="red", font.main=4)
title(xlab="Days", col.lab=rgb(0,0.5,0))
title(ylab="Total", col.lab=rgb(0,0.5,0))
legend(1, max_range[2], c("Sport","Family"), cex=0.8,
       col=c("blue","red"), pch=21:22, lty=1:2);
```       
{% include figure image_path="/assets/data/data/plot.gif" caption="Animation of the plot process" %}

## Visualizations 101

No matter if you produce publication quality graphics or quick and dirty visualizations, remember some guiding principles and traps illustrated in the upcoming figures.

For further reading, have a look at e.g. [Kelleher & Wagner 2011](https://www.sciencedirect.com/science/article/pii/S1364815210003270){:target="_blank"}. To get some inspiration, the [R Graph Gallery](https://www.r-graph-gallery.com/){:target="_blank"} is also a good place to start (but it relies on the ggplot2 library, not on the basic R plotting functions).



## Test your knowledge!
<iframe src="https://geomoer.github.io/moer-h5p-content/h5p-standalone-1.3.x/demo/base-r-unit09-creating.html" width="1090" height="600" frameborder="0" allowfullscreen="allowfullscreen" allow="geolocation *; microphone *; camera *; midi *; encrypted-media *"> </iframe><script src="https://h5p.org/sites/all/modules/h5p/library/js/h5p-resizer.js" charset="UTF-8"></script> 


<!--
## Further reading

add some day
-->
