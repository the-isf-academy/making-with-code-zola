---
Title: "[Resources]"
---

# Resources

This page will be home to helpful tips and tricks of Pandas and Matplotlib. Think of these resources as as an FAQs (frequently asks questions).

*Feel free to let a teacher know if you have any suggestions of what we should add.*

## Creating a Frequncy Table

When analyzing a CSV of our media history, we'll often see duplicates. For example with Netflix data, if I've watched an entire season of 'Friends', there will be multiple rows with for which the column 'tv_show' is 'Friends'. If we use `.count()` to find the total number of rows in the 'tv_show' column this will not give us an accurate number of unique tv_shows watched. This will simply give us the total number of episodes of tv shows watched.

To find the number of unique tv shows watched, we can create a new frequency dataframe. 

Consider this `.csv` file: 
> The columns are `tv_show_title` and `season`
>
> Each row is an episode of tv watched. 
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

```python3
frequency_series.index
```

> ```
> Index(['Brooklyn Nine-Nine', 'Friends', 'Community', 'Gilmore Girls',
>        'Queer Eye'],
>       dtype='object')
> ```

```python3
frequency_series.values
```

> ```
> array([118,  50,  48,  45,  32])
> ```