---
title: 0. Pet Lab
#draft: true
---

# Pet Lab
Today we will be learning about `Classes`. `Classes` are are what we use to create `Objects`.

## [0] Setup
{{< code-action "Start by making a new folder in your" >}} `cs9` **folder.**
```shell
cd Desktop/cs9
mkdir unit_02
cd unit_02
```

{{< code-action "Then, clone your starter code." >}} Be sure to change `YOUR-GITHUB-USERNAME` to your actual Github username.
```shell
git clone https://github.com/the-isf-academy/lab-pets-YOUR-GITHUB-USERNAME.git
```

## [1] Creating your own pet
{{< code-action "Open the Pet class in the Python shell" >}}
```shell
python3 -i pet.py
```
{{< code-action "Create your Pet" >}}
```shell
>>> my_pet = Pet()
```
The first thing you'll do with your pet is give it a name.
<br>
{{< code-action "Name your pet" >}} I've named mine Ajax. You can name yours whatever you'd like
```shell
>>> my_pet.set_name("Ajax")
```

{{< code-action "Have your pet introduce itself" >}}
```shell
>>> my_pet.introduce()
Hi, Im Ajax
```

{{< code-action "Try out these other methods in the terminal." >}} What happens if you try to get your pet to take two naps in a row? Or play twice in a row without napping in between?
```shell
>>> ajax.play()
>>> ajax.nap()
```

{{< code-action "You can exit from the shell interface by typing" >}} `^D`.
Your pet and its name will not be saved.

## [2] What type of animal is your pet?
### [Adding a new property]
{{< code-action "Open pet.py in atom" >}}
```shell
atom pet.py
```
If you look in the Pet class, you can see on lines 3-5 that we have three `properties`. `Properties` are variables that belong to a specific pet. Here we have 3 properties, `name`, `tired`, and `bored`.
```python {linenos=table, hl_lines=["3-5"],linenostart=1}
class Pet:
    def __init__(self):
        self.name = None #The pet's name
        self.tired = False #Tells us if the pet is tired
        self.bored = True #Tells us if the pet is bored
```
<br>
{{< code-action "Add a species property to the class." >}} It will work just like the `name` `property` does.


### [Adding a new method]

If you scroll down to lines 7-8, we see an example of a `method`. A `method` is similar to a function. The only difference is that a `method` belongs to a certain `class`, like `Pet`.
This particular `method` saves the name of the pet.

```python {linenos=table, linenostart=7}
def set_name(self, name):
    self.name = name #Saves the pet's new name
```
Just like the name property, we need to be able to set the species of our pet.

{{< code-action "Add a new method called set_species." >}} It will work just like the `set_name` method does, except instead of setting `self.name`, it will set `self.species`.
### [Testing your changes]
Let's see if your changes are working!

{{< code-action "Test your changes by typing these in the terminal one at a time." >}} You can set your species to whatever kind of pet you want!
```shell
python3 -i pet.py #open up the shell with the pet class
>>> my_pet = Pet() #create your pet
>>> my_pet.set_species("fox") #set the species of your pet
>>> my_pet.species #see if it worked
fox
```
Remember, when you're finished using the shell, you can exit by typing `^D`.
Your pet and its species will not be saved.

### [Using the species property]
Right now, the `introduce` `method` just has the pet say their name.

```python {linenos=table, linenostart=10}
def introduce(self):
    print("Hi, I'm", self.name)
```
<br>

{{< code-action "Edit the introduce function so that your pet will also tell you its species." >}}

{{< code-action "Test the updated introduce method using the shell." >}} If you need a reminder of how to do this, check the earlier examples at the beginning of the lab in the `Creating your own pet` section.


## [2] Teaching your pet new tricks
### [What's wrong with my pet]
Wouldn't it be nice if your pet could tell you whether it wanted to play or take a nap? Right now, the only way to know for sure is look at the `properties`: `tired` and `bored`. If `tired` is `True`, then the pet needs a `nap()`. If `bored` is `True`, the pet wants to `play()`.

{{< code-action "Add a new method called so that your pet can tell you what's wrong." >}} Here is an example of what 
<br>

Right now, we have two ways we can interact with our pet: `nap()` and `play()`.
{{< code-action "Add two new properties: self.hungry and self.toilet" >}}
<br>

{{< code-action "Edit the status method to include whether your pet hungry and whether it needs the toilet" >}}


## [3] Upgrading the Interface

{{< code-action "In interface.py, upgrade it to include other stuff" >}}
