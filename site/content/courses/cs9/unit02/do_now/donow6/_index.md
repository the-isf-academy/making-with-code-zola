---
title: "6. Uno Cards"
type: checkup
---
# Uno Cards

In this Do Now, we will explore how to use the Card class.  

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
atom donow6.py
```

{{< code-action "Copy and paste the starter code below:" >}}
```python
class Card(object):
    """A Deck has many Card objects.
    Args:
        color (str): Color of the card
        number (int): number on the card
    """

    def __init__(self, color, number):
        """constructor for new instance of Card
        """
        self.color = color
        self.number = number

def scenario():
    hand = []
    ### 🖥️ YOUR CODE GOES HERE 🖥️ ###

scenario()
```

---

## Use the Cards

{{< figure src="images/courses/cs9/unit02/donow0_6.png" width="400px" >}}

It's up to you to use the `Card` class to illustrate the following scenario:

0. Emily draws the 4 cards shown above and adds them to her **hand**
0. Emily looks at the **number** and **color** of each card in her hand
0. Emily removes the last card from her hand

{{< expand "Tips for using lists" >}}

```python
list.append(item) #adds an item to a list

list.pop() #removes the last item from the list

for item in list: #goes through each item in the list, one by one
```

{{< /expand >}}

{{< code-action >}} **Use the `Card` in the `scenario()` function to illustrate the scenario above**

{{< code-action "Test your code to ensure it works as expected by running:" >}} `python3 donow6.py`

{{< deliverables "Push to Github." >}}

Push your `donow6.py` to Github.


{{< /deliverables >}}
