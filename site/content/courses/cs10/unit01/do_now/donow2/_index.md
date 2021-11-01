---
title: 2. More Parsing
type: checkup
---

# More Parsing

Sometimes you need to organize the data depending on if something exists in it. Let's practice that now. 

{{< code-action "Create a new file" >}}
```shell
cd Desktop/cs10
cd do_now
atom do_now_2.py
```

{{< code-action "Copy and paste the code block below." >}}

```python
pets = {
    'john': {
        'dogs': 4,
        'fish': 10
    },
    'paul':{
        'cats': 2,
        'hampsters': 1
    },
    'george':{
        'dogs': 5,
        'snakes': 9
    },
    'ringo':{
        'spiders': 3,
        'dragons': 5
    }
}

def has_dog(adict):
    for name, pets in adict.items():
         #### YOUR CODE GOES HERE ####


has_dog(pets)
```

{{< code-action "Finish the" >}} `has_dog()` **function to print if each person that has a dog or does not have a dog.**

The final output should look something like:
```shell
john has a dog.
paul does not have a dog.
george has a dog.
ringo does not have a dog.
```
---

{{< aside "Does something exist in a dictionary?" >}}
Given the dictionary,
```python
ages_dict = {
    'anna': 16,
    'elsa': 21,
    'peter': 55,
    'paul': 45
}
```

You can check if something exists in it with this syntax,
```python
'anna' in ages_dict
```

This will return:
```shell
True
```
{{< /aside >}}

