---
title: 1. Average Prices
type: checkup
---
# Do Now

<br>
{{< code-action "First, navigate to your unit_01 folder, and create a sub-folder to store your `Do Now` assignments." >}} You'll use this folder to store your Do Now problems in the future.

```shell
cd Desktop/cs10 
cd unit_01
mkdir do_now
```

## Average Prices
A certain swimmer can swim 10 laps before she is too tired to continue. However, when we run the code, it seems like she can only swim 4 laps before she's too tired. You will need to debug and fix the issue by <b>code-tracing</b>.

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

{{< code-action "Create a new file" >}}
```shell
atom do_now_1.py
```

{{< code-action "Copy and Paste the swimming code into your new document, the run it." >}} <mark> Use print() statements to figure out what is going wrong, and then fix the code. </mark>
