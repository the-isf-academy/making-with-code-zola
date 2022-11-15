---
title: While loops
type: resource
---

In addition to `for` loops which run for a set number of iterations, Python has another type
of loop. `while` loops iterate until a particular condition is met.

{{< tabs id="While-loops" >}}

{{< tab "Video Explanation" >}}

{{< youtube "D0Nb2Fs3Q8c" >}}
{{< /tab >}}

{{< tab "Text Explanation" >}}
### Conditions
`while` loops use conditions just like `if` statements. You can use operators to compare
values in or to generate `True` or `False` conditions. Looping until a condition is met
can be useful when you are getting getting input from a user, generating random variables,
or repeatedly applying a transformation to a value.

```python
user_input = -1
while user_input < 1 and user_input > 10:
    user_input = input("Tell me a number between 1-10 (inclusive): ")
```

### While True / Break
You can also make `while` loops run indefinitetly by setting the condition to `True` like
this: `while True:`. This can be useful when you want to loops a program repeatedly.

To stop a loop like this, you can use a `break` statement. Once the program reaches the
`break`, the loop will exit.

You've actually already seen an example of this kind of loop at the beginning of the lab.

```python
speed(10)
while True:
    drawing = input("What would you like me to draw? ")
    size = int(input("How big should I draw it? "))
    if drawing == "square":
        for i in range(4):
            forward(size)
            right(90)
    elif drawing == "quit":
        break
    else:
        print("Sorry, I don't know how to draw that...")
```
{{< /tab >}}
{{< /tabs >}}


