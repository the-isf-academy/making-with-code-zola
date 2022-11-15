---
title: "4. Advanced Character Creation"
type: checkup
draft: true
---
# Advanced Character Creation

In this Do Now, you will extend the `Character` class from the previous Do Now. 

---

## Inheritance 

Games often have different types of characters, all with the same basic functionality. We create this behvaior with [inheritance](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_6).


Consider this `Person` class. They have a `name`. 
```python
class Person:
    def __init__(self):
        self.name = None

    def set_name(self,name):
        self.name = name
```
> ```shell
> >>> p = Person()
>>> p.set_name('Ringo')
>>> p.name
>'Ringo'


We can create a **child class** of `Person` called `Student` that inherets the `name` property and a `grade_level` property. 
```python
class Student(Person):
    def __init__(self):
        self.grade_level = None

    def set_name(self,name):
        self.name = name

    def set_grade_level(self,grade):
        self.grade_level = grade
```
> ```shell
> >>> s = Student()
>>> s.set_name('George')
>>> s.name
>'George'
>>> s.set_grade_level(9)
>>> s.grade_level
>9

---

## Set up

{{< code-action "First, navigate to your cs9/donows/unit_02 folder" >}} `unit_02` **folder.**

```shell
cd Desktop/cs9
cd cs9-donows-YOUR-GITHUB-USERNAME
cd unit_02
```

{{< code-action  >}} **Open the `donow2.py` document**
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
---

## Child Class: Hero

{{< code-action  >}} **Create a child class of `Character` called `Hero`.** The hero will inheret all of the features of `Character`, as well as the following features:
- `inventory` property that can store multiple items 
- `add_inventory(item)` method that adds `item` to the `inventory` 

{{< code-action >}} **Enter the Python shell to test the `Hero` class: `python3 -i donow2.py`** 
```shell
>>> h = Hero()
>>> h.set_name("Mario")
>>> h.inventory
[]
>>> h.add_inventory("mushroom")
>>> h.add_inventory("gold coins")
>>> h.inventory
["mushroom","gold coins"]
```

{{< code-action >}} **Test the `Character` class. It should not have an `inventory`.**
```shell
>>> c = Character()
>>> c.inventory
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Character' object has no attribute 'inventory'
```

{{< deliverables "Push to Github." >}}

Push your `donow2.py` to Github.


{{< /deliverables >}}

---

### [Extension: Unique Introduce]

{{< code-action >}} **Override the `introduce()` method for the `Hero` class.** When tested, it should look something like this: 

```shell
python3 -i donow2.py

>>> h = Hero()
>>> h.set_name("Mario")
>>> h.introduce()
"Hi, I'm Mario. The hero of this story."
>>> c = Character()
>>> h.set_name("Luigi")
>>> c.introduce()
"Hi, I'm Luigi."
```


