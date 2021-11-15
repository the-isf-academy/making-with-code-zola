---
title: "0. Phone"
type: lab
# draft: true
---

# Phone

In this lab we will further explore how to create a user interface for a Class. 

## [0] Setup

{{< code-action "Create a new folder in your" >}} `cs10` directory.

```shell
cd Desktop/cs10
mkdir unit-review
```

{{< code-action "Clone your repository" >}}
``` shell
git clone https://github.com/the-isf-academy/lab-phone-YOUR-USERNAME.git
```

This repository has three files:
- `phone.py`
- `interface.py`
- `view.py`

## [1] Interface

Your job is to create the command line interface for the `Phone`. 

{{< look-action "Start by taking a look at the" >}} `Phone` **class**.
```shell
atom phone.py
```
> Notice what properties it has and what methods it has


{{< write-action "With the class in mind, create a flow chart for the type of interactions you'd like your interface to have in your notebook." >}} 


{{< expand "Here is an example of a basic interface, but feel free to cutomize yours!" >}}


```shell
--- Welcome to the Phone creator ---
Would you like a Phone? yes
What operating system would you like? iOS

[Phone Menu]
0) Play Game
1) Watch Video
2) Send Text
3) Take a Picture
4) Check Battery
5) Recharge
6) Put phone away
What would you like to do with your phone? 1
You just watched an unboxing video

[Phone Menu]
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
{{< /expand >}}

---
### [interface.py and view.py]

{{< code-action "Start by running" >}} `interface.py`
```shell
python3 interface.py
```

At the moment, all it does is welcome to the service. **It's up to you to add the bulk of the interface.**

You will do this by editing `view.py` and `interface.py`.
- `view.py` will hold the `View` class that implements all of the terminal output
- `interface.py` will hold the logic of how the user interacts with the `Phone` class

{{< code-action "Implement your interface flowchart by editing the" >}} `view.py` and `interface.py` files. 

--- 

## [2] Extension: additional features

{{< code-action "Add additional features to your interface." >}} Ideas include but are not limited to:
- error checking (e.g. allowing user to input again if their input was incorrect)
- restricted to only creating certain types of operating systems
- ability to pick what game you play




