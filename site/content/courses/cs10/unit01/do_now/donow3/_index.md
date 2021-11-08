---
title: 3. Restaurant
type: checkup
---
# Restaurant

In this do now, we are going to review data structures. 

{{< code-action "Create a new file." >}}

```shell
cd Desktop/cs10/unit_01
atom donow1.py
```

## Waiter

We are going create the scenario of waiter taking a customer's order.

Your file must include: 
- Asking the customer for their name
- Asking the customer what they would like for drink
- Asking the customer what they would like for food
- Asking the customer what they would like for dessert 
- Repeating the customer's order

{{< code-action "Code the scenario of a waiter taking an order." >}}


It should look something like this:
```shell
What is your name? Ringo

What would you like to drink? iced lemon tea
What would you like to eat? ramen
What would you like for dessert? oreo ice cream

Ringo ordered:
iced lemon tea
ramen
oreo ice cream
```


### [Helpful Functions]

Take a look at the functions below to help you write the scenario. 

#### To get user input and store it in a variable:
```python
month = input("What month were you born in? ")
```


#### To add items to a list:
```python
month_list = ['jan']
month_list.append('feb')
print(month_list)
```
> This will output:
>
> `['jan','feb']`

#### To print the first item in a list:
```python
month_list = ['jan','feb','march']
print(month_list[0])
```
> This will output:
>
> `'jan'`


## Extension

Sometimes the customer would like to change their order. 

{{< code-action "Before repeating the order to the customer, ask the customer if they would like to change their meal." >}}
> *Consider: how will you re-structure the data to easily switch only the of part of the order they'd like to change?*
