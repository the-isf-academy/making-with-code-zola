---
title: Variables
type: resource

---
One of the most powerful tools of programming is the variable: a storage container for information in your programs.

{{< tabs >}}
{{< tab "Video Explanation" >}}
{{< youtube id="DaOVh3WKm_U" >}}
{{< /tab >}}
{{< tab "Text Explanation" >}}
You are probably familiar with variables in math. ("Solve for x: `2x + 4 = 3x`") In math problems, the goal
is often to figure out the secret value of a variable. Once you figure it out, the problem is finished.
Variables work differently in computer science:

- You can create them whenever you want. In fact, you already made one. Remember typing `number = 5` above?
You made a variable called "number" and set its value to 5. This is called *declaring* a variable.
- In computer science, you get to decide what value variables have, and you can change them whenever you want.
This is called *assigning* values to variables.
Try this:

```shell
>>> name = "Willie"
>>> "my name is " + name
```

- You can call them whatever you want (no spaces though!) In math, variables have names like `x`, `y`, and `t`.
In computer science, we usually call them things like `number_of_coins_in_my_hand` or `direction_my_character_is_facing`
because it's less confusing.

You can think about variables as little boxes in your computer's memory that store things so you can use
them later.

{{< figure src="/images/courses/cs9/unit00/00_variables_memory.png" title="Variables in memory" >}}
{{< /tab >}}
{{< /tabs >}}
