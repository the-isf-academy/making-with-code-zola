---
title: "0. iPhone"
type: lab
# draft: true
---

# iPhone

In this lab we will further explore how to create a user interface for a Class. 

## [0] Setup

{{< code-action "Create a new folder." >}}

```shell
cd Desktop/cs10/unit_01
mkdir iPhone_lab
```

{{< code-action "Copy and paste the starter code." >}}

```python
class iPhone:
    def __init__(self,version):
        self.version = version
        self.battery = 100

    def play_game(self):
        self.battery = int(self.battery - self.battery * .2)
        
    def send_text(self):
        self.battery = int(self.battery - .01)

    def watch_video(self):
        self.battery = int(self.battery - self.battery*.1)

    def take_picture(self):
        self.battery = self.battery - 1

    def recharge(self,amount_recharge):
        new_charge_amount = self.battery+amount_recharge

        if new_charge_amount > 100:
            self.battery = 100
```

## [1] Interface

Your job is to create the command line interface for the `iPhone`. 

{{< write-action "In your notebook, create a flow chart for the type of interactions you'd like your interface to have." >}} 

{{< code-action "In a new file, use your flow chart as a reference to create the user interface for the " >}} `iPhone` **object.**
```shell
atom iphone_interface.py
```

Here is an example of a basic interaction, but feel free to cutomize yours.

```shell
--- Welcome to the iPhone creator ---
Would you like an iPhone? yes
What type of iPhone would you like? 13

[iPhone Menu]
0) Play Game
1) Watch Video
2) Send Text
3) Take a Picture
4) Check Battery
5) Recharge
6) Put phone away
What would you like to do with your phone? 1
You just watched an unboxing video

[iPhone Menu]
0) Play Game
1) Watch Video
2) Send Text
3) Take a Picture
4) Check Battery
5) Recharge
6) Put phone away
What would you like to do with your phone? 4
Your battery is at 90%
```

## [2] Additional Feature

{{< code-action "Add additional features to your interface." >}} Ideas include but are not limited to:
- error checking (e.g. allowing user to input again if their input was incorrect)
- restricted to only creating certain types of iPhones
- ability to pick what game you play




