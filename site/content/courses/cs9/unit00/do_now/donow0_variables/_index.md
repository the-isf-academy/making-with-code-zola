---
title: 0. Variables
type: checkup
# draft: true
---

# Do Now

Do Now exercises are quick problems at the start of class to help you sharpen your coding skills.


{{< code-action "Open your Terminal and clone this Do Now onto your laptop" >}} 

```shell
mwc update
```


## Swimming fatigue
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

{{< code-action "Create a new document" >}}
```shell
atom do_now_1.py
```

{{< code-action "Copy and Paste the swimming code into your new document, the run it." >}} <mark> Use print() statements to figure out what is going wrong, and then fix the code. </mark>
