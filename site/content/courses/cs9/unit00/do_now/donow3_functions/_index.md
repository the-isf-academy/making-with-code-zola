---
title: 3. Mystery Code Trace
type: checkup
---

# Mystery Code Trace

{{< code-action "Look at the code below. Without running the code, answer the following questions in your notebook:" >}}

> - What will the program draw? 
>   - Draw an example. 
> - What is the purpose of the `size` paramter in the `full(size)` function? 
> - How will the drawing of `full(100)` differ from the drawing of `full(200)`?

```python {linenos=table}
from turtle import *

def triangle(size):
    color("green")
    begin_fill()
    right(60)
    for i in range(3):
        forward(size)
        right(120)
    left(60)
    end_fill()

def top(size):
    for i in range(3):
        triangle(size)
        penup()
        left(90)
        forward(.3*size)
        right(90)
        pendown()

def bottom(size):
    width = size*.1
    height = size
    
    color("brown")
    begin_fill()
    for i in range(2):
        forward(width)
        right(90)
        forward(height)
        right(90)
    end_fill()
    forward(width//2)
    
def full(size):
    bottom(size)
    penup()
    left(90)
    forward(.3*size)
    right(90)
    pendown()
    top(size)

full(90)

input()
```
<br>
