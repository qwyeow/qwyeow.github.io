# Title
> summary


# Seaborn Plots

this is a test jupyter notebook blog post.

```python
arrays = [['Falcon', 'Falcon', 'Parrot', 'Parrot'],
          ['Captive', 'Wild', 'Captive', 'Wild']]

index = pd.MultiIndex.from_arrays(arrays, names=('Animal', 'Type'))
df = pd.DataFrame({'Max Speed': [390., 350., 30., 20.]},
                  index=index)
```

```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>Max Speed</th>
    </tr>
    <tr>
      <th>Animal</th>
      <th>Type</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="2" valign="top">Falcon</th>
      <th>Captive</th>
      <td>390.0</td>
    </tr>
    <tr>
      <th>Wild</th>
      <td>350.0</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">Parrot</th>
      <th>Captive</th>
      <td>30.0</td>
    </tr>
    <tr>
      <th>Wild</th>
      <td>20.0</td>
    </tr>
  </tbody>
</table>
</div>



```python
df.groupby(level=0).mean()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Max Speed</th>
    </tr>
    <tr>
      <th>Animal</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Falcon</th>
      <td>370.0</td>
    </tr>
    <tr>
      <th>Parrot</th>
      <td>25.0</td>
    </tr>
  </tbody>
</table>
</div>



```python
df.groupby(level="Type").mean()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Max Speed</th>
    </tr>
    <tr>
      <th>Type</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Captive</th>
      <td>210.0</td>
    </tr>
    <tr>
      <th>Wild</th>
      <td>185.0</td>
    </tr>
  </tbody>
</table>
</div>



# What is a scatter plot?

A scatter plot (aka scatter chart, scatter graph) uses dots to represent values for two different numeric variables. The position of each dot on the horizontal and vertical axis indicates values for an individual data point. Scatter plots are used to observe relationships between variables.

### When you should use a scatter plot

Scatter plots’ primary uses are to observe and show relationships between two numeric variables. The dots in a scatter plot not only report the values of individual data points, but also patterns when the data are taken as a whole.

Identification of correlational relationships are common with scatter plots. In these cases, we want to know, if we were given a particular horizontal value, what a good prediction would be for the vertical value. You will often see the variable on the horizontal axis denoted an independent variable, and the variable on the vertical axis the dependent variable. Relationships between variables can be described in many ways: positive or negative, strong or weak, linear or nonlinear.

### A Seaborn Scatter Plot

```python
import seaborn as sns
sns.set(style="white")

# Load the example mpg dataset
mpg = sns.load_dataset("mpg")

# Plot miles per gallon against horsepower with other semantics
sns.relplot(x="horsepower", y="mpg", hue="origin", size="weight",
            sizes=(40, 400), alpha=.5, palette="muted",
            height=6, data=mpg)
```




    <seaborn.axisgrid.FacetGrid at 0x7fb0c5182850>




![png](/images/jupyter_notebook_blog_post_files/output_9_1.png)

