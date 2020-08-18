---
Title: Style guide
---

# Style guide

## Localization

Our goal is to produce curriculum which can be used anywhere, but every
learning environment is specific. Therefore we will sometimes need to make
assumptions about how things are set up. When local assumptions are unavoidable,
please tag them with the [local shortcode]({{< ref "dev/syntax.md#local" >}}). 

{{< local >}}

You can use the [`teacher` shortcode]({{< ref "dev/syntax.md#teacher" >}}) as a reference to the teacher's name (currently "{{< teacher >}}"). 

## Text and action indicators
Throughout the site, we use a variety of symbols to indicate ccertain actions
associated with the content. Here is a list of the symbol, it's short code, and how it should be used:

| Symbol                | Shortcode                                                  | Usage                                            |
|:---------------------:|:----------------------------------------------------------:|--------------------------------------------------|
| {{< look-action >}}   | [`look-action`]({{< ref "dev/syntax.md#look-action" >}})   | There is something here you should read or watch |
| {{< code-action >}}   | [`code-action`]({{< ref "dev/syntax.md#code-action" >}})   | Do something in code or with your Terminal       |
| {{<  write-action >}} | [`write-action`]({{< ref "dev/syntax.md#write-action" >}}) | Write or draw something on paper or a Google Doc |

## Code

- Use fenced code blocks to represent source code. 

  ```shell
  $ pwd
  /Users/chris
  ```
  ```python3
  def fibb():
      "An iterator over the fibonacci sequence"
      a, b = 1, 0
      while True:
          yield a
          a, b = a + b, a
  ```
- For interactive shells such as the command prompt and Python's REPL, show
  output as it will appear to users. 
  ```python3
  >>> 1+2
  3
  ```
- Use [line numbers](https://gohugo.io/content-management/syntax-highlighting/#highlighting-in-code-fences)
  when the text will refer to specific elements of the code. 
- Use `$` to represent the command prompt. When filesystem locations are
  important, use `~/Desktop/cs9/unit_00$`.


## Open issues

We have a number of stylistic conventions sprinkled throughout the curriculum.
Let's try to approach these declaratively using shortcodes so we can change them
later if we want to. For example, various uses of emoji to indicate the kind of
task.
