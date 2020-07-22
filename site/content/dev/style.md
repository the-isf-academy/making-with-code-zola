---
Title: Style guide
---

# Localization

Our goal is to produce curriculum which can be used anywhere, but every
learning environment is specific. Therefore we will sometimes need to make
assumptions about how things are set up. When local assumptions are unavoidable,
please tag them with `LOCAL` in a [devnote]({{< ref "dev/syntax.md#devnote" >}}). 

{{< devnote >}}LOCAL{{< /devnote >}}

When someone later wants to further localize the curriculum, they can search for
`LOCAL`.

You can use the [`teacher` shortcode]({{< ref "dev/syntax.md#teacher" >}}) as a reference to the teacher's name. 

Even {{< teacher >}} sometimes makes mistakes. 

# Code

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


