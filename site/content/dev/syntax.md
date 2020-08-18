---
title: Syntax
---

# Syntax

*Making with Code* is a static site built with [Hugo](https://gohugo.io/). You
will need to understand the basics of the Hugo framework to contribute. 
Content is written in markdown, which you can probably pick up just by looking at 
some of the existing content.

## Custom Shortcodes

### include_module

Includes the full content of a module (from the same unit) in a lesson.

```
{{</* include_module "lab_terminal_adventure" */>}}
```

### ref_module

Creates a link to a module (from the same unit) in a lesson.

```
{{</* ref_module "lab_terminal_adventure" */>}}
```

### ref_practice

Creates a link to a practice description. May be used on any content page. 

```
{{</* ref_practice "activity/help_queue" */>}}
```


### devnote

Use for notes and TODO items. Content within `devnote` is highlighted and only
shown in the `dev` environment. 

```
{{</* devnote */>}}
This lesson went horribly. Need to revise.
{{</* /devnote */>}}
```

### local

Use to mark content which is unavoidably localized to a particular learning
environment. At least later users can search for these and make appropriate
updates. 

```
{{</* local */>}}
When you finish, turn this worksheet in to Moodle. 
```

### teacher
Uses the teacher's name, which can be configured via a 
[site param]({{< ref "dev/config#Teacher" >}}). 
```
Even {{</* teacher */>}} sometimes makes mistakes. 
```

### look-action
Inserts a symbol to indicate that the reader should read or watch something.
Can be configured via a [site param]({{< ref "dev/config#LookAction" >}}).

{{< look-action >}} Check out this great example of [abstraction](https://www.youtube.com/watch?v=oHg5SJYRHA0)!

### code-action
Inserts a symbol to indicate that the reader should do something in code or in their Terminal.
Can be configured via a [site param]({{< ref "dev/config#CodeAction" >}}).

{{< code-action >}} Run the following command in your Terminal:
```
$ telnet towel.blinkenlights.nl
```

### write-action
Inserts a symbol to indicate that the reader should write or draw something on paper or a Google Doc.
Can be configured via a [site param]({{< ref "dev/config#WriteAction" >}})

{{< write-action >}} Sketch what you think your computer would look like if it had the personality of Scooby Do.

### checkpoint

Adds a checkpoint where students should stop working on a lab and check in with
a teacher. A self-closing tag will use a default message; otherwise a custom
message may be provided. 

{{< checkpoint />}}

```
{{</* checkpoint /*/>}}
```

{{< checkpoint >}}
Take a break.
{{< /checkpoint >}}

```
{{</* checkpoint */>}}
Take a break.
{{</* /checkpoint */>}}
```
