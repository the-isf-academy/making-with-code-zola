---
title: 3. Run Tracker 
type: checkup
---
# Do Now: Run Tracker

{{< code-action "First, navigate to your" >}} `cs9-donows/unit_01` **folder.**

```shell
cd Desktop/cs9
cd cs9-donows-YOUR-GITHUB-USERNAME
cd unit_01
```

{{< code-action "Create a new document" >}}
```shell
atom donow3.py
```

## Run Tracker 

Ms. Brown is trying to get fit again and wants a way to easily track how far she's been running. She has written a function to find the mean of a list, but she needs help finishing her program.

#### This program should:

0. ask the user how many runs they would like to average
0. ask the user to input their distance for each run 
0. calculate the average distance 
0. print the average distance to the user

```python
# unit01 - donow3.py
####################

def mean(alist):
    total_sum = 0
    for num in alist:
        total_sum = total_sum + num
    mean_val = total_sum / len(alist)
    return mean_val


print("----- Running Distance Average Calculator -----")
num_runs = int(input("How many runs would you like to average? "))
print("-"*48)

run_list = []

### 💻  YOUR CODE GOES HERE 💻  ###

```

{{< code-action "Let's start by running" >}} `donow3.py`. It runs without bugs, however it only  asks the user how manys they would like to average. It doesn't collect any run information, calculate the average, or communicate the average to the user. 

{{< code-action "It's up to you to complete the program!" >}}

The output of this program should look something like this: 
```shell
----- Running Distance Average Calculator -----
How many runs would you like to average? 3
------------------------------------------------
How far was a run number in kms? 7.8
How far was a run number in kms? 6.5
How far was a run number in kms? 8.2
--------------------
You ran an average of 7.5kms.
```

{{< deliverables >}}
{{< code-action "Be sure to" >}} `push` **your work to Github.**

{{< /deliverables >}}

---

### [Extension: Improved User Experience]

Currently the program works perfectly, however it does not communicate detailed information to the user. 

{{< code-action "Improve the print statements to communicate more information." >}}

The improved output should look something like this:

```shell
----- Running Distance Average Calculator -----
How many runs would you like to average? 3
------------------------------------------------
How far was run number 0 in kms? 7.8
How far was run number 1 in kms? 6.5
How far was run number 2 in kms? 8.2
--------------------
You ran an average of 7.5kms over 3 runs.
```

---

### [Extension: Recording more Info]

Ms. Brown would like to not only record her distance, but record the date of the run and the time. 

{{< code-action "Expand on the current program to include:" >}}
- storing the date, time, and distance of each run
- storing the km/hr of each run 
- calculating the average of km/hr, time ran, and distance ran 
- communicating the averages to the users
