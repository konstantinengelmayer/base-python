---
title: Importing Data
toc: TRUE
toc_float: TRUE
header:
  image: /assets/images/unit_images/u06/header.png
  image_description: "computer"
  caption: "Photo by [Free-Photos](https://pixabay.com/photos/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=336373) [Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=336373)"
---

<!--more-->

## Importing csv data with python using pandas
Reading or writing tabulated data into or from a data frame is a quite common task in data analysis. Based on the csv data provide is can be really easy or sometimes also a bit cumbersome. If the separator of your csv is `,`, the decimal separator is `.` and you have a header for each column you can normally use the `read_csv()` function with the path of you `.csv` without any additional parameters.

```python
import pandas as pd

# Reading the CSV file
df = pd.read_csv('path/to/your/file.csv')
```
When ever one of these parameters are different than the default you need to change them manually. To see all available parameters of the function you can type `pd.read_csv?` So for European `.csv` files it often looks like this:
```python
df = pd.read_csv('path/to/your/file.csv', sep = ';', decimal = ',')
```

## Real World Example

This (example is taken from [here](https://www.regionalstatistik.de/genesis/online/){:target="_blank"}) . It contains data about the area of different landuse types. 


```python
import pandas as pd

# Reading the CSV file
df = pd.read_csv('/AI001_gebiet_flaeche.csv', skiprows=4, header=0, sep=';', decimal=',')
```
#### Explanation of Parameters
1. `filepath_or_buffer`: The path to the CSV file.
2. `skiprows=4`: Skips the first four lines (useful if the first few lines contain metadata rather than data).
3. `header=0`: Specifies that the first non-skipped row contains the header.
4. `sep=';'`: Defines the column separator.
5. `decimal=','`: Defines the decimal separator used in the dataset.

A quick way to check if everything is fine is to display the first few lines of the data file using the `head` method (without the 2, it will print 5 lines as a standard setting).

```python
print(df.head(2))
## Output:
##      X X.1                  X.2
## 1 1996  DG          Deutschland
## 2 1996  01   Schleswig-Holstein
##   Anteil.Siedlungs..und.Verkehrsfläche.an.Gesamtfl.
## 1                                              11,8
## 2                                              10,8
##   Anteil.Erholungsfläche.an.Gesamtfläche
## 1                                    0,7
## 2                                    0,7
##   Anteil.Landwirtschaftsfläche.an.Gesamtfläche
## 1                                         54,1
## 2                                         73,0
##   Anteil.Waldfläche.an.Gesamtfläche
## 1                              29,4
## 2                               9,3
```

## Writing Data to CSV Files
Writing data to a CSV file is as straightforward as reading it. You can use the `to_csv` method from the pandas DataFrame.
```python
df.to_csv('path/to/your/output_file.csv', sep=',', decimal='.', index=False)
```
1. `path_or_buf`: The file path or object where the CSV data will be written.
2. `sep=','`: Defines the column separator.
3. `decimal='.'`: Defines the decimal separator.
4. `index=False`: Omits the DataFrame index from the output file.


## Test what you've learned so far!

<iframe src="https://geomoer.github.io/moer-h5p-content/h5p-standalone-1.3.x/demo/base-r-unit06-pathanddata.html" width="1090" height="450" frameborder="0" allowfullscreen="allowfullscreen" allow="geolocation *; microphone *; camera *; midi *; encrypted-media *"> </iframe><script src="https://h5p.org/sites/all/modules/h5p/library/js/h5p-resizer.js" charset="UTF-8"></script> 





<!--
## Further reading

add some day
-->
