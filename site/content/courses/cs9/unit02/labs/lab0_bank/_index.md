---
title: 0. Bank Lab
resources:
- name: Bank class map
  src: images/courses/cs9/unit02/02_00_bank_class_map.png
---
{{< devnote >}}
CS1/CS2 links in [0] Setup, bring BISF documentation (https://cs.fablearn.org/docs/central/index.html) into Making with Code?
{{< /devnote >}}

# 0. Bank Lab


## Overview
You have been hired by the Bank of ISF (BISF) to check for security flaws in a
new accounting system they're condsidering. You goal is to try to hack into the bank and report back on potential ways to improve the bank's security. Along the way, you'll learn more about our programming focus this unit: Object-Oriented Programming (OOP)

Your tasks:

1. Learn about using OOP in Python
2. Understand the Bank and Account class BISF has developed as part of their accounting system
3. Add a new function to BISF's system
4. Break into the bank -- and propose security fixes for the vulnerabilities

## [0] setup

💻 **TODO:** In your `cs9` directory, create a `unit_02` directory and a `lab_02_00` directory inside it. Navigate to the `lab_02_00` directory and create an individual repository for the lab using the following links:

If you are in **CS 1**, [click here](https://classroom.github.com/a/_wfZ_PFC).

If you are in **CS 2**, [click here](https://classroom.github.com/a/fE66Qqj8).

💻 **TODO:** In your terminal, navigate to the lab_02_00 directory.

## [1] Object oriented programming

In this week's lesson, we talked about how object oriented programming uses classes of objects to group related properties and functionalities.

👀 **TODO:** To learn about how classes are implemented in Python, check out the resources below. At the very least, watch the videos in each section:

- [12.1 Why learn about classes?](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_1)
- [12.2 Defining and Creating Simple Classes](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_2)
- [12.3 Adding Methods to Classes](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_3)

## [2] Understanding the Bank and Account Classes

💻 **TODO:** To get a sense of how the banking system works, start by running `central.py`.

This will execute a series of transactions depositing and withdrawing money from banks. Note that both the `Bank` and the `Account` objects report back what's going on. Let's try to figure out what's happening

💻 **TODO:** Open all the files in this directory using `atom .`

There's a lot going on here! Fortunately, BISF has done a great job documenting their banking program with [these documentation pages](https://cs.fablearn.org/docs/central/index.html).

👀 **TODO:** Since this may be your first time looking through documentation, watch this video for an example about how to read documentation and use it to make a program:

<iframe width="560" height="315" src="https://www.youtube.com/embed/RXr6-_EzPRg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Draw it out

Note that the `Bank` class imports the `Account` class. This is because each `Bank` object uses `Account` objects to store information about each account in the bank. It is very common for objects to contain other objects. When dealing with multiple classes, mapping how each of the parts interact can be a good to help understand what's going on:

{{< figure src="images/courses/cs9/unit02/02_00_bank_class_map.png" width="400px" >}}

### Try it out

Let's put your new understanding of the BISF banking system classes to the test.

💻 **TODO:** In `part2.py`, use the `Bank` class to create the scenario described below:

- The bank HSBC opens and runs a promotion: for each of the first 10 people to open an account, HSBC will automatically deposit 10 times the account number into the account (so Account0 get $0, Account1 gets $10, Account2 gets $20...)
- 10 people open accounts (with the name `"Account0"`, `"Account1"`, `"Account2"`, ... `"Account9"`). When each account opens, HSBC automatically deposits the promotion money
- BISF opens and runs a counter promotion: For each of the first 10 new accounts, BISF will match the first deposit into each account (deposit the value again).
- Seeing an opportunity to make money, each of the 10 people who initially opened an account at HSBC:
    - checks their HSBC account balance
    - withdraws the full amount
    - opens a BISF account (with the same name as their HSBC account)
    - deposits their money.
    - gets the BISF promotional matching deposit (as a separate transaction).

💻 **TODO:** Run `python test_lab.py -k part2` to test this part of the lab.

*Note:* the test harness checks both the end state and the logs from the banking operations so it is important that you follow the scenario in order.

*Hint:* If you get stuck, try looking through through `test_output.txt` to make sure your output aligns with the expected output.

## [3] Transfer money

To make sure that you're familiar with the banking system, BISF wants you to implement a `transfer()` function at the end of the `Bank` class. BISF has already defined this function in the banking system's documentation. [Check out the documentation](https://cs.fablearn.org/docs/central/bank.html#bank.transfer) to see the specifics of the function you should implement.

💻 **TODO:** Write the `transfer()` function and test it by running `python test_lab.py -k transfer`.

*Note:* you may find it helpful to reuse functions that have already been implemented in the `Bank` or `Account` class

*Hint:* The test script uses different scenarios to check to make sure your function handles a variety of interactions. If you get stuck, read through the scenarios printed when you first run the test script to make sure your function is behaving normally.

## [4] Identify security flaws

Now that you are familiar with the banking system, it's time to get to work trying to hack the system 💰💰💰

There is a security bug somewhere in the banking program which allows users to get more money than they should.

💻 **TODO:** Your job: find the bug and fix it. Run `python test_lab.py -k bug` to check your work.

*Hint:* If you don't know where to start looking for the bug, the test scenario could be a good place to start. 🔎

*Aside*: There is a MAJOR security flaw in BISF's banking software that we can't fix: properties in python can be edited from anywhere that has access to the state of the program. That means that a savvy programmer who understands classes and properties could easily directly affect the `balance` property of each Account without having to go through the banking system. To see how this works in effect, consider (and try out!) the code below:

```python
    hsbc  = Bank("HSBC")
    hsbc.add_account("Han")
    hsbc.deposit("Han", 100)    # a normal deposit

    hsbc.accounts["Han"].balance = 10000000000000    # Ms. Han hacking the system!
```

There is still a security bug within the parameters of the banking system, but the code above shows that, even after you fix the bug, you're probably going to want to pick a more secure program if you go into banking 😅
