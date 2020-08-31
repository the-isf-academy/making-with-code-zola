---
title: The Python shell
type: resource
<<<<<<< HEAD

=======
>>>>>>> 04f571b5a57496cf6ec4eac0a20a1af0dda47094
---
Usually, we write Python code in a file using Atom and then run it using Terminal. There's another way to run
Python, which is really nice for when you just want to mess around or do a quick test.

{{< tabs "python-shell" >}}
{{< tab "Video Explanation" >}}
coming soon!
{{< /tab >}}
{{< tab "Text Explanation" >}}

{{< code-action >}} Open Terminal, navigate
to your computer science directory and type `python`.

```shell
~$ cd Desktop/cs9
~/Desktop/cs9$ python
Python 3.7.3 (default, Mar 27 2019, 09:23:15)
[Clang 10.0.1 (clang-1001.0.46.3)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

See how the prompt changed to `>>>`? That tells you you're in Python world. You can type Python code here and
it will run. Let's try it out. Type the following, and make sure you get the same response.

```shell
>>> 1+1
2
>>> 123456 + 654321
777777
>>> number = 5
>>> number * number
25
>>> "I am " + "a robot"
'I am a robot'
>>> exit()
~/Desktop/cs9$
```

Once you exit the Python shell, all your work is lost. So it's not a good way to do serious work, but it
works great as a fancy calculator.

```shell
>>> 1+1
2
>>> 123456 + 654321
777777
```
{{< /tab >}}
{{< /tabs >}}
