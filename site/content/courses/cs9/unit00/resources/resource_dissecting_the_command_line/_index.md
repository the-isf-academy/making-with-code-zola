---
title: Dissecting the command line
type: resource
draft: true
---
## Dissecting the command line
{{< tabs "dissecting-command-line" >}}
{{< tab "Video Explanation" >}}
coming soon!
{{< /tab >}}

{{< tab "Text Explanation" >}}
We've already used a lot of commands to help us navigate Terminal. Let's take a deeper look at 
what we're actually doing when we type commands in the command line.

```shell
TEA-JWOLF:cs9 jwolf$ ls
env     unit_00
```

Lines in the command line have two parts.

{{< columns >}}

**The Prompt** `TEA-JWOLF:cs9 jwolf$` – This part is provided by the Terminal, so we don't need
to type it. The prompt can vary on different computers and shell programs, but generally it shows 
things like the machine we're using (`TEA-JWOLF`), the directory we're currently in (`cs9`), and 
the current user (`jwolf`).

<--->

**The Command** `ls` – In the line above, we're entering the `ls` command to list everything 
in the current directory.

{{< /columns >}}

### Commands
Now, let's see what goes into a command. Some commands like like `pwd` (which shows us the path
to our current location) appear solo:

```shell
TEA-JWOLF:cs9 jwolf$ pwd
/Users/jwolf/Desktop/cs9
```

### Arguments
Other commands require *arguments* that follow the command. An *arguement* is a specification for
where or what you want the command to run. For example, the `cd` command requires a path to a
directory as an arguement:

```shell
TEA-JWOLF:cs9 jwolf$ cd unit_00/
```

Some commands require multiple arguments. `mv` moves a directory or file to another location and
requires two paths as arguements:

```shell
TEA-JWOLF:cs9 jwolf$ mv file.txt unit_00/
```

### Options
Finally, the functionality of commands can often be changed with *options* which are placed between
the command and any arguments the command takes. An *option* is a minor difference in the way the 
command works. For example, the `rm` command normally removes (or deletes) a file:

```shell
TEA-JWOLF:unit_00 jwolf$ rm bad_file.txt
```

However, with the `-d` option, `rm` will also remove a directory:

```shell
TEA-JWOLF:unit_00 jwolf$ rm -d bad_directory
```

### More commands
You can learn more about the arguments and options associated with a command by googling it. If
you're interested in learning more commands, [this](https://www.codecademy.com/articles/command-line-commands) 
is a good place to start.

{{< /tab >}}
{{< /tabs >}}
