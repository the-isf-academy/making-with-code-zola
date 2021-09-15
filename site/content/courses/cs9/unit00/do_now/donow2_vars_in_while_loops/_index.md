---
title: 2. Is it Friday yet?
type: checkup
---

<p style="font-size:32px;font-weight:bold">Is it Friday yet?</p>

{{< code-action "Create a new document" >}}
```shell
atom do_now_2.py
```

Look at the code below. What do you think the code is trying to do? When should the while loop stop?

{{< code-action "Copy and Paste the following code into your new document, the run it." >}}
```shell
python3 do_now_2.py
```
<mark> Use print() statements to figure out what is going wrong, and then fix the code. </mark>

```python
today = "Monday"
tomorrow = "Tuesday"
while today != "Friday":
    yesterday = today
    today = tomorrow

    if today == "Sunday":
        tomorrow = "Monday"
    elif today == "Monday":
        tomorrow = "Tuesday"
    elif today == "Tuesday":
        tomorrow == "Wednesday"
    elif today == "Wednesday":
        tomorrow = "Thursday"
    elif today == "Thursday":
        tomorrow = "Friday"
    elif today == "Friday":
        tomorrow = "Saturday"
    elif today == "Saturday":
        tomorrow = "Sunday"

print("Yay it's Friday!")
```
<br>
