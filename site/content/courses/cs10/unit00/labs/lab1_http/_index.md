---
title: "1. HTTP"
type: lab
---

# HTTP: How Computers Communicate

The Internet may be humanity's most profound invention. A global
network of computers talking to one another, allowing possible for people all
over the world to interact. In this lab, we will start learning about *how*
computers talk with one another. 

{{< expand "Vocabulary" >}}

- A **protocol** is a set of rules for how to behave or communicate. 
  Human speech has many protocols: when you must be serious and when you may tell jokes; 
  when you must show respect and when you may be warm and friendly. Human
  protocols are usually somewhat flexible, but computer protocols are usually very
  strict. Either you follow all the rules or communication fails. 
- **Hypertext** was an early word for webpage content--it's "hyper"
  because any part of the text can be a link connecting to other texts, just
  like the way ideas spark other ideas. 
- **HTTP** stands for "**Hypertext Transfer Protocol**." It's a set of rules for how
  computers ask each other for content, and how they reply. 
- **HTML** stands for "**Hypertext Markup Language**," the grammar of websites.
  HTML is a code full of tags like `<body>` and `<div>`. Putting it all
  together, HTTP describes how comptuers ask each other for content; HTML describes 
  how they should format the content when sending web pages. 

{{< /expand >}}

## The basic rules of HTTP

- Communication starts when one computer (the client) sends a Request to another computer (the server). 
  Here's the HTTP request your browser makes every time you go to `cs.fablearn.org`. (The comments aren't part of it, they are just there for you.)

  ```shell {linenos=table}
  GET /index.html HTTP/1.1                    // I want index.html
  Accept: */*                                 // Any format is fine
  Host: cs.fablearn.org                       // Hey, Im talking to you
  ```

- Unless there is some problem, the server sends a Response. 
  For example: 

  ```shell {linenos=table, linenostart=4}
  HTTP/1.1 200 OK                                 // This is the Response
  Content-Length: 2081                            // I am sending a lot
  Content-Type: text/html                         // I am sending HTML
  Date: Tue, 18 Aug 2020 19:23:28 GMT             // This is when I sent it
  Last-Modified: Tue, 18 Aug 2020 15:46:28 GMT    // There is new content
  
  <!DOCTYPE html>                                 // Here it comes!
  <html lang="en">                                // Here is your webpage
      . . . 
  <p><em>Making with Code</em> is a new, old 
  approach to teaching computer science 
  based in Constructionism.</p>
      . . .
  ```
- `GET` (line 1) is the request **method**. The other common method is `POST`. You 
  send a `GET` request when you want some content but are not planning to make
  any changes. You send a `POST` request when you are trying to make a change, 
  like logging in or making a purchase.
- `200` (line 4) is the response status code. 
  - `200` means success.
  - `300` means you're looking in the wrong place
  - `400` means you did something wrong.
  - `500` means, "Sorry, the server broke!" 
- Lines 2 and 3 are request headers. Lines 5-8 are response headers. They provide
  more detail about what is being requested and what is being sent back.

## Let's try it

In this lab we are going to practice getting and sending HTTP requests using a
nice little tool called `http`. 

{{< code-action >}}  Let's install it:

```shell
$ pip install httpie
```

{{< code-action >}} There is a Riddle server running at `138.68.28.249:5000`. Let's see
which riddles are available for guessing: 

```shell
$ http GET 138.68.28.249:5000/riddles/all

HTTP/1.0 200 OK
Content-Length: 102
Content-Type: application/json
Date: Wed, 09 Sep 2020 21:06:24 GMT
Server: Werkzeug/1.0.1 Python/3.5.2

{
    "riddles": [
        {
            "correct": 0,
            "guesses": 0,
            "id": 1,
            "question": "What is black and white and red all over?"
        }
    ]
}
```

{{< code-action >}} Do you know the answer? Try posting a guess. Note that we are now using
a different URL, `138.68.28.249:5000/riddles/guess`, because we want to guess the answer
to a riddle. It is common for POST requests to send a payload with the request. 
In this case, the payload is a parameter called `id` specifying which riddle we
are guessing, as well as `guess`.

```shell
$ http POST 138.68.28.249:5000/riddles/guess id=1 guess="A banana"

HTTP/1.0 200 OK
Content-Length: 134
Content-Type: application/json
Date: Wed, 09 Sep 2020 21:06:54 GMT
Server: Werkzeug/1.0.1 Python/3.5.2

{
    "correct": false,
    "guess": "A banana",
    "riddle": {
        "correct": 0,
        "guesses": 1,
        "id": 1,
        "question": "What is black and white and red all over?"
    }
}
```

Oh well. Maybe you can do better. Once you guess the right answer, try adding your own riddle 
to the server. The [riddle documentation](https://github.com/cproctor/riddle_server) will help here, but here 
is a cheatsheet of all the URL routes:

| Method | URL                                | Required Payload     | Action                                                                                   |
| ------ | ---------------------------------- | -------------------- | ---------------------------------------------------------------------------------------- |
| `GET`  | `138.68.28.249:5000/riddles/all`   |                      | Returns a list of all the riddles, without answers.                                      |
| `GET`  | `138.68.28.249:5000/riddles/one`   | `id`                 | Returns the riddle if it exists. (Otherwise, it returns an error with status code 404.)  |
| `POST` | `138.68.28.249:5000/riddles/new`   | `question`, `answer` | Creates a new riddle (with an automatically-assigned id). Returns the riddle.            |
| `POST` | `138.68.28.249:5000/riddles/guess` | `id`, `guess`        | Checks whether the guess is correct. In the response, `correct` is `True` or `False`.    |

{{< checkpoint >}}
Once everyone in your group has successfully posted a riddle to the
server and guessed the answer to a few riddles, check in with a teacher.
{{< /checkpoint >}}

## Your own Riddle server

The Riddle server is a pretty simple program. While it is running, it waits for
requests to come in and responds when they do. Let's set it up on your Raspberry
Pi.

{{< code-action >}} First, `ssh` into your Pi. Then clone and install the Riddle
server:

```shell
$ cd cs10/unit_00
$ git clone https://github.com/cproctor/riddle_server.git
$ cd riddle_server
$ pip install -r requirements.txt
```

{{< code-action >}} Now run the Riddle server. 

```shell
./run.sh
```

You will see the server's startup message, and then it will sit there, waiting.
Try accessing the server from your laptop. You need to know the Pi's IP address, 
and then use port 5000, something like `192.168.1.204:5000`. Ask a friend for
their Pi's IP address and try accessing their Riddle server. 

You will see an access log as clients access your Riddle server. When you are
ready to shut it down, press `Control + C`.

{{< checkpoint >}}
Once everyone in your group has deployed the Riddle server to their Pi, accessed
someone else's Riddle server, and had someone access theirs, check in with a
teacher. 
{{< /checkpoint >}}

## Writing a client

This riddle server is a lot of fun. But it's not very fun having to write all
these HTTP requests into the Terminal. What if we had a program which took care
of making these requests for us? A program like this is called a **client**. Any
app which uses the Internet is a client; it is constantly making HTTP requests
to a server to send and receive information. 

Our client is going to have two faces. The `View` will interact with the human
user and the `API` (application programming interface) will interact with the 
server. The API takes care of all the connection details, and the View takes
care of providing a good user experience. 

{{< code-action >}} Starter code for the client is provided in the
`riddle_server` repo. Download it *onto your laptop*.

```
$ cd cs10/unit_00
$ git clone https://github.com/cproctor/riddle_server.git
$ cd riddle_server/riddle_client
$ ls
api.py	view.py
```

{{< code-action >}} Now try running the client. 

```
$ python view.py
```

It runs! Until it doesn't. The view is fully-functional, however the API
is not. Your job is to finish the API methods which haven't been written yet: 

- `get_riddle`
- `get_random_riddle`
- `add_riddle`

You will know it works once you can fully run the view without any crashes. 

Tips:
- The API uses the [requests](https://requests.readthedocs.io/en/master/)
  library to send and receive HTTP requests. You can read the documentation, 
  or you can just copy the usage examples already present in `api.py`.
- Use the [riddle server documentation](https://github.com/cproctor/riddle_server)
  to make sure you're using the correct URL and sending the right parameters 
  for each request. Otherwise you'll be getting errors back from the server.

{{< checkpoint >}}
Once everyone in your group has a fully-functional client, check in with a
teacher. 
{{< /checkpoint >}}

## Improving the client

Once you have a fully-working client, make it better. Here are a few ideas:

- Display the riddles' difficulty. 
- Keep track of the player's score.
- Give the player prizes, or let them unlock secret modes, if they get a high
  enough score.
- Track the player's correct and incorrect guesses and give the player 
  riddles of the appropriate difficulty. (Hint: `Riddle.difficulty`, 
  defined in [riddle_server/riddles/model.py, line 98](https://github.com/cproctor/riddle_server/blob/3412a4a1043fc591dfc46541be9060ad271ae374/riddles/model.py#L98),
  may be useful. You can calculate a player's skill the same way we calculate a
  riddle's difficulty.)
