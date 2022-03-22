---
Title: "[Resources]"
---

# Resources

This page will be home to helpful tips and tricks of `Pandas` and `MatPlotLib`. Think of these resources as as an FAQs (frequently asks questions).

> Simply click on a header on the right sidebar, to jump to a topic.

*Feel free to let a teacher know if you have any suggestions of what we should add.*

---

## Creating a Frequency Table and Graph

When analyzing a CSV of our media history, we'll often see duplicates. 

Consider this `.csv` file with Netflix data: 
> The columns are `tv_show_title` and `season`
>
> Each row is an episode of TV watched. 
```shell
tv_show_title,          season,     
Brooklyn Nine-Nine,     Season 1
Brooklyn Nine-Nine,     Season 1
Brooklyn Nine-Nine,     Season 1
Friends,                Season 2
Friends,                Season 1
Community,              Season 1
Community,              Season 1
```

If we use `.count()` to find the total number of rows in the `tv_show_title` column this will *not* give us an accurate number of unique tv shows watched. This will simply give us the total number of episodes of tv shows watched.

**To find the number of unique tv shows watched, we can create a new frequency table in a pandas `series`.** 



```python3
frequency_series = df['tv_show_title'].value_counts()
frequency_series
```

> ```
> Brooklyn Nine-Nine    118
> Friends                50
> Community              48
> Gilmore Girls          45
> Queer Eye              32
> Name: tv_show_title, Length: 5, dtype: int64
> ```

**To access just the tv shows, we can use `.index` to get a list of the tv show titles**

```python3
frequency_series.index
```

> ```
> Index(['Brooklyn Nine-Nine', 'Friends', 'Community', 'Gilmore Girls',
>        'Queer Eye'],
>       dtype='object')
> ```

**To access just the frequency values, we can use `.values` to get a list of the number of times each show was watched.**
```python3
frequency_series.values
```

> ```
> array([118,  50,  48,  45,  32])
> ```

**We can then use `MatPlotLib` to create a bar chart.** 

```python3
# Using the frequency_series, we can great a bar graph. 
plt.bar(frequency_series.index,frequency_series.values)

# Adds a label to the x-axis
plt.xlabel('TV Shows')

# Adds a title to the y-axis
plt.ylabel('Amount Watched')

# To add a title to the plot
plt.title('Relationship between TV Show and Number of Episodes Watched')

# Displays Plot
plt.show()
```

{{< figure src="images/courses/cs9/unit01/resources_01.png" width="100%" >}}

---

## Adding Color to your Charts

Adding custom colors to our charts can make them look more beautiful. **To start, create a list of colors:**

```python3
color_list = ['#2CBDFE', '#47DBCD','#F5B14C', '#9D2EC5','#661D98']
```
> This list should be a list of `strings` containing the *hex code* for each color.
>
> Google has a great built in [color picker](https://www.google.com/search?q=color+picker&rlz=1C1GCEA_enUS897US897&oq=color+picker&aqs=chrome.0.69i59j0i512l9.1382j0j7&sourceid=chrome&ie=UTF-8&safe=active&ssui=on).

### [Bar Chart]

To incorporate these colors into a bar chart:
```python3 {linenos=table, hl_lines=["4"]}
plt.bar(
    frequency_series.index,
    frequency_series.values,
    color=color_list
)
```


{{< figure src="images/courses/cs9/unit01/resources_02.png" width="100%" >}}

### [Pie Chart]

```python3 {linenos=table, hl_lines=["5"]}
plt.pie(
    frequency_series.values,            
    labels = frequency_series.index,  
    autopct='%1.1f%%',
    colors=color_list
)     
```


{{< figure src="images/courses/cs9/unit01/resources_03.png" width="100%" >}}

### [Advanced Color]

If you're interested learning how to customize your graphs further, take a look at [`seaborn`](https://seaborn.pydata.org/index.html). 

Seaborn is another Python library that is built on top of MatPlotLib. 

---