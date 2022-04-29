---
title: "2. Character Creation"
type: checkup
---
# Character Creation

In this Do Now, you will extend the `Character` class from the previous Do Now. 

---

## Set up

{{< code-action "First, navigate to your cs9/donows/unit_02 folder" >}} `unit_02` **folder.**

```shell
cd Desktop/cs9
cd cs9-donows-YOUR-GITHUB-USERNAME
cd unit_02
```

{{< code-action  >}} Open the `donow2.py` document"
```shell
atom donow2.py
```

Your code should look something like this

```python
#############
# unit02
# donow2.py
#############

class Character: 
    def __init__(self):
        self.name = None
        self.health = 10

    def set_name(self,name):
        self.name = name

    def introduce(self):
        print("Hi I'm {}.".format(self.name))

    def lose_health(self,amount):
        self.health = self.health - amount
    
    def gain_health(self,amount):
        self.health = self.health + amount
```

## Extending the Character

Games often have different types of characters, all with the same basic functionality. We create this behvaior with inheritance.

{{< code-action  >}} **Create a child class of `Character` called `Hero`. The hero will have the following extensions:
- `inventory` property that can store multiple times 
- `add_inventory(item)` method that can adds `item` to the `inventory` 
- `view_inventory()` method that prints out each item in the `inventory`

{{< code-action >}} "Enter the Python shell to test the `Hero` class. 
```shell
python3 -i donow2.py

>>> h = Hero()
>>> h.set_name("Mario")
>>> h.inventory
[]
>>> h.add_inventory("mushroom")
>>> h.view_inventory()
Current inventory: 
- mushroom
```

{{< code-action >}} "Test the `Character` class. It should not have an `inventory`.
```shell
python3 -i donow2.py

>>> c = Character()
>>> c.inventory
ERROR
```

{{< deliverables "Push to Github." >}}

Push your `donow2.py` to Github.


{{< /deliverables >}}

---





