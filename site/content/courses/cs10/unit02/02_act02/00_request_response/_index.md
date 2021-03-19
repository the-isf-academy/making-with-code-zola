---
title: 1. Request/Response Lifecycle
---

# The Request/Response Lifecycle

In this lab, you'll explore a Django app and make some changes to how it handles
the request/response lifecycle. 

{{< write-action >}} **At the end of the lab, each student will 
turn in the answers to the questions in the lab.** Make sure you actually 
{{< look-action >}} read the content of this lesson and 
{{< code-action >}} do the exploring parts, or you might not understand the 
questions. (And we want you to be ready for the rest of the unit.)

{{< code-action >}} Let's get started by checking out the sample app. 
 
```shell
$ git clone https://github.com/the-isf-academy/cs10_webapp_base
$ cd cs10_webapp_base
$ pip install -r requirements.txt
```

{{< code-action >}} Now have a look around using the `tree` command.
```shell
$ tree .
```

You'll meet some of these files today. For now, the most important file to know
about is `manage.py`. You'll always run this file when you want Django to do
anything. 

{{< code-action >}} To see a list of available commands, run:
```shell
$ python manage.py help
```

## Hello

{{< code-action >}} Let's start up the app and test it out. Run:
```shell
$ python manage.py runserver 8000
```

Now the server is waiting for requests. Head over to your web browser and 
navigate to [http://localhost:8000](http://localhost:8000). 

{{< checkpoint >}}

1. What is the first color? (You should see it on the webpage).

{{</ checkpoint >}}

- Change the color
- See how params propagate from the view to templates
- Change the name param and the color param. 

## Request 2

- URL params (wire this in)
- class-based view
- using a model

## Request 3

- Implement the view
- Import the model









## Wrapping up

In this lesson, you learned the basic structure of a Django app, by looking at
the files and tracing their execution as they handled a basic request and
response lifecycle. 

This lesson guided you through the first steps of the official 
[Django tutorial](https://docs.djangoproject.com/en/3.1/intro/tutorial01/#creating-a-project); 
have a look. We didn't do everything, but you should recognize some of the steps
over there. The sooner you get familiar with the style of Django's
documentation the better.




