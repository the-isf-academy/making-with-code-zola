---
title: 1. Parsing
type: checkup
---
# Do Now

<br>
{{< code-action "First, navigate to your unit_01 folder, and create a sub-folder to store your `Do Now` assignments." >}} You'll use this folder to store your Do Now problems in the future.

```shell
cd Desktop/cs10 
cd unit_01
mkdir do_now
```

## Parsing
In computer science, to parse means to translate some kind of data into another kind of data. 

For example, to take the list, `name_list = ['Paul', 'Ringo', 'John', 'George']`, and turn into the string, `'The members of the Beatles are Paul, Ringo, John, and George'`.

Let's practice parsing a dictionary. 

{{< code-action "Create a new file" >}}
```shell
atom do_now_1.py
```

{{< code-action "Copy and paste the code block below." >}}

```python
grocery_prices = {
    'fruit':
    {
        'bananas': 5.30,
        'apples' : 3.35,
        'dragonfruit': 6.15
    },
    'meats':
    {
        'pork': 72.00,
        'beef': 46.90
    },
    'drinks':
    {
        'vitasoy': 53.00,
        'orange juice': 29.90,
        'coffee': 42.00
    }
}


def average_cost(adict,category):
    ### YOUR CODE GOES HERE ###
    return

print(average_cost(grocery_prices,'fruit'))
print(average_cost(grocery_prices,'meats'))
print(average_cost(grocery_prices,'drinks'))
```

{{< code-action "Finish the" >}} `average_cost()` **function to calculate the average cost of a given food category.**

The final output should like:
```shell
average price of fruit 4.933333333333334
average price of meats 59.45
average price of drinks 41.63333333333333
```


{{< aside "Iterating through a Dictionary" >}}
Given the dictionary,
```python
ages_dict = {
    'anna': 16,
    'elsa': 21,
    'peter': 55,
    'paul': 45
}
```

To iterate through it you can use:
```python
for key,val in ages_dict.items():
    print(key,val)
```

This will output:
```shell
anna 16
elsa 21
peter 55
paul 45
```
{{< /aside >}}


<hr>

## Abstracting the solution 

{{< code-action "Edit your exisiting function so the user can find the averages of each category without having to know the category name." >}} Test your updated function using the dictionary below.

Use the following dictionary to test your solution:
```python
game_dictionary = {
    'indie pc':
    {
        'stardew valley': 93.27,
        'celeste' : 155.51,
        'eastward': 186.62
    },
    'ps5':
    {
        "assassin's creed": 875.00,
        'fifa 21':789.00,
        'rachet and clank': 628.00
    },
    'boardgames':
    {
        'pictionary': 260.00,
        'uno': 84.90,
        'risk': 240.00
    }
}
```
