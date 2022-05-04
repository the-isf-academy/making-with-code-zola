---
title: "4. Octopus Card"
type: checkup
---
# Octopus Card

In this Do Now, you will use an Octopus Card object to illustrate a scenario.  

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
atom donow4.py
```

{{< code-action "Copy and paste the starter code below:" >}}
```python
class OctopusCard:
    def __init__(self, name):
        self.name = name
        self.balance = 0

    def top_up(self,amount):
        self.balance = self.balance + amount

    def pay(self, amount):
        self.balance = self.balance - amount

    def change_owner(self,name):
        self.name = name

def scenario():
    ### 🖥️ YOUR CODE GOES HERE 🖥️ ###

scenario()
```

---

## Use the Octopus Card

It's up to you to use the `OctopusCard` class to illustrate the following scenario:

0. Link gets an Octopus card 
0. Link checks the balance of the card
0. Link adds 250HKD to the card
0. Link takes 10 mini-buses. Each ride costs 12HKD.
0. Link buys a Vitasoy at 7/11 with the card that costs 7HKD
0. Link checks the balance of the card
0. Link gives his card to Zelda

{{< code-action >}} **Use the `OctopusCard` in the `scenario()` function to illustrate the scenario above**

{{< code-action "Test your code to ensure it works as expected by running:" >}} `python3 donow4.py`

{{< deliverables "Push to Github." >}}

Push your `donow4.py` to Github.


{{< /deliverables >}}







