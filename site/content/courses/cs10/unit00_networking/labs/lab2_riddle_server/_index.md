---
title: "2. Server"
type: lab
slug: lab_riddle_server
# repo_url: https://github.com/the-isf-academy/lab_riddle_server.git
# init_action: init
draft: true
---

# Riddle Server

In this lab we are going to learn how the riddle server is made.

---

## [0] Local Riddle Server

You are each able to run a locally hosted riddle server on your laptop using Banjo.

{{< code-action "Start by going into the lab folder" >}}
```shell
cd ~/desktop/making_with_code/cs10/unit00_networking/lab_riddle_server
```

{{< code-action "Enter the Poetry shell" >}}
```shell
poetry shell
```

---

### [Starting the Serve]

{{< code-action "Now, let's start your local server." >}}
```shell
banjo
```
```shell
No changes detected in apps 'app', 'banjo'
Operations to perform:
  Apply all migrations: admin, app, auth, contenttypes, sessions
Running migrations:
  No migrations to apply.
No changes detected in apps 'banjo', 'app'
Operations to perform:
  Apply all migrations: admin, app, auth, contenttypes, sessions
Running migrations:
  No migrations to apply.
Performing system checks...

System check identified no issues (0 silenced).
September 16, 2022 - 02:40:21
Django version 4.1.1, using settings 'banjo.settings'
Starting development server at http://127.0.0.1:5000/
Quit the server with CONTROL-C.
```

---


### [Accessing the Server]

{{< look-action " You can now visit this server in your web browser, just as you did with the riddler server hosted on the internet: " >}} [http://127.0.0.1:5000/riddesl/all](http://127.0.0.1:5000/riddles/all)

**In order to send requests to the other endpoints, you will need always have 2 Terminal windows open.**
- 1 window will run the server
- 1 window will send `HTTP` requests

{{< code-action "Open another Terminal window." >}} You can either open a new tab, `command+t`, or open a new window with `command+n`.

{{< code-action "View all the riddles in the second Terminal window." >}}
```shell
http get http://127.0.0.1:5000/riddesl/all
```

{{< look-action " Look at the Terminal window running the server. Notice how it recorded your request." >}}
```shell
[16/Sep/2022 02:44:20] "GET /riddles/all HTTP/1.1" 200 1069
```

Your version of the riddle server only has the 2 endpoints:
- `/riddles/all`
- `/riddles/guess`

{{< checkpoint >}}

{{< code-action "Explore both endpoints via the Terminal and be sure to successfully:" >}}
- view all riddles without the answers
- guess a riddle
{{< /checkpoint >}}

---

## [1] Exploring Banjo

This server is written using Banjo, a wrapper for [Django](https://www.djangoproject.com/). It allows users to quickly create models with a persistant database and API.

Banjo apps must have an `app` folder. Within the app folder must be two files: `models.py`, `views.py`. The `database.sqlite` file is created when the server is first started. It is stored at the same level as `app`. Here is an example file structure:
```shell
lab_riddle_server
|
└──app
|   ├──models.py
|   └──views.py
└──database.sqlite
```
- `models.py` - A model is essentially an abstracted class. Just as a class has properties, a model has fields. When defining a model's fields, you must specify the data type.
- `views.py` - The views are where you define the API functionality. Here is where you decide what the `endpoints` are and the type of `HTTP` request it will require.

**In this lab, we are going to be primarily focused on the `views.py` file.**

{{< code-action "Let's start by opening up the primary folder:" >}} `app`

```shell
atom app
```


{{< checkpoint >}}

{{< write-action >}}  **Complete the worksheet.**

{{< code-action >}} **It will require you to edit code, run tests, and experiment with the riddle server.**
{{< /checkpoint >}}


---

## [3] Deliverables


{{< deliverables >}}  

**Once you've successfully completed the worksheet be sure to fill out [this Google form](https://docs.google.com/forms/d/e/1FAIpQLSfgWwxFI8SotkBsredlpQejYI2fHzJDQ-2oZgdYTq1ZQO_zjw/viewform?usp=sf_link).**

{{< /deliverables >}}
