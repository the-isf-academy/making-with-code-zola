---
title: "2. Character Creation"
type: checkup
---
# Character Creation

In this Do Now, you must complete the `Character` class. 

---

## Set up

{{< code-action "First, navigate to your cs9/donows/unit_02 folder" >}} `unit_02` **folder.**

```shell
cd Desktop/cs9
cd cs9-donows-YOUR-GITHUB-USERNAME
cd unit_02
```

{{< code-action "Create a new document" >}}
```shell
atom donow2.py
```

{{< code-action "Paste in this starter code." >}}

```python
#############
# unit02
# donow2.py
#############

class Character: 
    def __init__(self):
        self.name = None

    def set_name(self,name):
        self.name = name

    def introduce(self):
        print("Hi I'm {}.".format(self.name))
```

## Completing the Character 

Currently, the `Character` class is quite simple. It has:
- 1 `name` property
- 1 method to set the `name`
- 1 method to print hello

{{< code-action "Start by running the file in the Python shell and testing its functionality: " >}} `python3 -i donow2.py`.

Let's make this Character a bit more complex. 

{{< code-action "Add the following characteristics to the " >}} `Character`:
- a `health` property that is initially set to 10 
- a `lose_health()` method that takes an `amount` as a parameter 
- a `gain_health()` method that takes an `amount` as a parameter 

{{< code-action "Test your code to ensure it works as expected." >}}

{{< deliverables "Push to Github." >}}

Push your `donow2.py` to Github.


{{< /deliverables >}}

---


### [Extension: Advanced Character Creation]

Currently, when you create a class it is initialized without a `name`. **But, what if you only wanted to be able to construct a class with a name?**

{{< code-action >}} **Add a parameter to the `Character` class so that it must be initialized with a `name`.**
> Look at [this](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_5) resource to learn about constructors. 

It will run this like:
```shell
>>> link = Character("Link")
```









