---
title: 2. Runtime Lifecycle
draft: true
---

# Django Runtime

In our first Django lab, we learned about the request/response lifecycle, how
Django's many different parts work together to serve responses to clients. 
In this second lab on Django, we will consider a longer lifecycle, how Django
works as a Python program from startup to shutdown. You will also learn about
different ways of running Django, and we'll go into a bit more detail about
requests and responses. 

This lab picks up where [Part I](courses/cs10/unit_02/00_request_response/_index.md) 
left off, so you should have the Colorama app checked out on your computer. 
{{< write-action >}} **At the end of the lab, each student will 
turn in the answers to the questions in the lab.** 

## Django management commands

Every time you run Django, you run `manage.py` with some command. In Part I, you
ran two management commands, `migrate` and `runserver`.
You also saw many more, when you ran `python manage.py --list`.  (You can learn
more about any command by running `python manage.py runserver --help`.) Let's
explore a few more commands. 

### Database management

Your app stores its state in a database. In other words, all its
records--usernames, content, never-ending records of every detail of user 
behavior, financial details (for apps like PayPal), your sexual orientation and who 
you find attractive (for dating apps), whether you have cancer (electronic medical 
records) ... Basically, if anyone ever got access to your app's database, 
they could steal all this information and it could be a disaster for your users. 
Unfortunately, this happens all the time. (This is a great reason for using a 
framework like Django rather than trying to do it all yourself.)

Somewhat less disastrous is the situation where an app accidentally loses its
own database, because of a careless programmer mistake (done that!), because a
hard drive fails, or perhaps because you forgot to pay your web hosting bill
(happened to a friend!) Users would find that their account no longer exist, nor
does any of their content. After a restart, the app would behave as if it had
just been launched for the first time. For apps in production (meaning they are
available to real-world users), regular database backups are essential. That
way, even if disaster strikes, at least you can restore the app to the way it
was this morning, or last week, or whenever you last backed up the database. 

Django has some nice built-in tools for database backups, which will provide us
with a chance to practice using some new management commands.

- Dump current data 
- Delete the database file.
- Load wikipedia fixture... wow! so many colors

## The shell 

- Practice exploring ORM queries using the shell
- Questions about how many colors exist, how many colors with red > 100, etc. 

## Settings

- Explain how settings work
- Some key settings. We will use 'hues_to_show` to decide how to represent the
  color pallete in `show_color`

## Logging

- Explain the purpose of logging. 
- Practice adding logging statement

## Adding a Color Detail route

- URL arguments
- Overriding get_context method in DetailView
- Using SETTINGS.hues_to_show to configure how to show one color with a bunch of
  other hues that (might) go with it.
