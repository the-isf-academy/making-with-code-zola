---
title: 0. Swimming
type: checkup
# draft: true

---
# Do Now

Do Now exercises are quick problems at the start of class to help you sharpen your coding skills.

<br>
{{< code-action "First, navigate to your unit_00 folder, and create a sub-folder to store your `Do Now` assignments." >}} You'll use this folder to store your Do Now problems in the future.

```shell
cd unit_00
mkdir do_nows
```

{{< code-action "Start by opening the Terminal cloning this lab onto your laptop." >}} As a reminder, we will run this command at the start of each lab.
```shell
mwc update
```
{{< code-action "In the Terminal, type the following command to open the lab folder." >}}
```shell
cd ~/desktop/making_with_code/cs9/unit00_drawing/dolab-loops
``` 

{{< code-action "Enter the Poetry Shell to start the lab." >}} As a reminder, we will run this command at the start of each lab, but only when we are inside a lab folder.
```shell
poetry shell
```
{{< aside "Exiting the poetry shell" >}}
When you want to exit the shell, you can type `exit` or `^D`
{{< /aside >}}

---

## Swimming fatigue
Sally can swim 10 laps before she is too tired to continue. However, when we run the code, it seems like she can only swim 4 laps before she's too tired. You will need to debug and fix the issue by <b>code-tracing</b>.

```python
laps = 0
for i in range(10):
    print()
    print("LAP ", i)
    if laps < 10:
        print('~~~swimming~~~')
        laps = laps + i
    elif laps >= 10:
        print("I can't swim any more, I'm too tired")
```
<br>

{{< code-action "Create a new document" >}}
```shell
atom do_now_1.py
```

{{< code-action "Copy and Paste the swimming code into your new document, the run it." >}} <mark> Use print() statements to figure out what is going wrong, and then fix the code. </mark>
