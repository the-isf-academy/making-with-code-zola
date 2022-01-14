---
title: 3. Hero Stats
type: checkup
draft: True
---

## One-to-one Relationships

Dictionaries can be used to show one-to-one relationships like how capitals are connected countries, how students are connected to grade levels, or how books are connected to authors. 

For example, take a hero in an adventure game:

```python
def create_character_traits():
    return {
        "courage": 8,
        "beauty": 4,
        "strength": 7,
        "empathy": 5
    }
```

{{< code-action >}} Open a python shell and import the `describe_character` and `create_character_traits` functions from the `dictionaries.py` file. Create a `character_traits` dictionary using the `create_character_traits` function and run the `describe_character` function:

```shell
>>> from dictionaries import describe_character, create_character_traits
>>> character_traits = create_character_traits()
>>> describe_character(character_traits)
You are foolhardy.
```

You can loop through a `dict` in almost the same way you can loop through a list:

```shell
>>> for trait, value in character_traits.items():
...     print("You have a {} value of {}.".format(trait, value))
You have a courage value of 8.
You have a beauty value of 4.
You have a strength value of 7.
You have a empathy value of 5.
```
