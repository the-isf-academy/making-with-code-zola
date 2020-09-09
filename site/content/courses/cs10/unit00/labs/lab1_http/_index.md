---
title: "1. HTTP"
type: lab
---

# HTTP: How Computers Communicate

The Internet may be humanity's most profound invention. A global
network of computers talking to one another, making it possible for people all
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
  how they should format the content. 

{{< /expand >}}

## The Basic Rules of HTTP

Communication starts when one computer (the client) sends a Request to another computer (the server). 

Everytime you visit a URL, your computer opens a connection with the server at that address and uses **HTTP Protocol** to recieve the content. For example, by visiting "cs.fablearn.org" you initiate a **GET Request** to recieve the *Making with Code* homepage from the server. 

A **GET Request** contains following: 

```shell
GET / HTTP/1.1
Host: cs.fablearn.org
```

Another frequently utilized request is a **POST request**. A `POST` request is sent when you are sending data to the server. For example, logging into an account or making an online purchase. 

A **POST Request** contains following: 

```shell
GET / HTTP/1.1
Host: cs.fablearn.org
```

Once the request has been recieved by the server, it responds with a by sending the client a **HTTP Response Status Code**. If a successful connection has been made, the server sends the content to the client. 

A successful **HTTP Status Code** contains the following:

```shell
HTTP/1.1 200 OK
Content-Type: text/html
```

The `Content-Type` tells your computer what type of data is being recieved. In this instance of "cs.fablearn.org", your computer recieves the HTML, Javacsript, CSS, and image files that make up the homepage of the site. 

{{<expand "Common Status Codes" >}}
- `200` means success.
- `300` means you're looking in the wrong place
- `400` means you did something wrong.
- `404` means the resource requested could not be found 
- `500` means, "Sorry, the server broke!" 

{{</expand>}}

<br>

{{< code-action >}} To see status codes in action:

0. Right click on any website and click "Inspect"
0. Select "Network" from the top tool bar in the devleoper tools
0. Hard refresh your page with "Command + Shift + R"
0. Find the URL under "Name"
0. Under the "Status" column you will see "200", signifiying a sucessful **GET** request

It's important to remember 




## Let's try it

In this lab we are going to practice getting and sending HTTP requests using a
nice little tool called `http`. 

{{< code-action >}}  Let's install it:

```shell
$ pip3 install httpie
```

{{< code-action >}} There is a Riddle server running at `138.68.28.249:5000`. Let's see
which riddles are available for guessing: 

```shell
$ http GET 138.68.28.249:5000

HTTP/1.0 200 OK
Content-Length: 189
Content-Type: application/json
Date: Tue, 18 Aug 2020 21:37:54 GMT
Server: Werkzeug/1.0.1 Python/3.5.2

{
    "riddles": [
        {
            "correct": 0,
            "guesses": 0,
            "id": 1,
            "question": "What is black and white and red all over?"
        },
    ...
```

{{< code-action >}} Do you know the answer? Try posting a guess. Note that the URL is now 
`138.68.28.249:5000/1` because we are guessing riddle #1. It is common for 
POST requests to send a payload with the request. In this case, the payload is a
parameter called `guess`.

```shell
$ http POST 138.68.28.249:5000/1 guess="A banana"

HTTP/1.0 200 OK
Content-Length: 134
Content-Type: application/json
Date: Tue, 18 Aug 2020 21:43:08 GMT
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

| Method | URL                    | Action                                                                                               |
| ------ | ---------------------- | ---------------------------------------------------------------------------------------------------- |
| `GET`  | `138.68.28.249:5000/`  | Returns a list of all the riddles, without answers.                                                  |
| `GET`  | `138.68.28.249:5000/x` | Returns the riddle with id `x` if it exists. (Otherwise, it returns an error with status code 404.)  |
| `POST` | `138.68.28.249:5000/`  | Creates a new riddle if `question` and `answer` are provided. The new riddle is returned.            |
| `POST` | `138.68.28.249:5000/x` | Accepts a `guess` for riddle `x` if it exists. The response says whether you were correct. |

{{< checkpoint >}}
Once everyone in your group has successfully posted a riddle to the
server and guessed the answer to a few riddles, check in with a teacher.
{{< /checkpoint >}}

## Your own Riddle server

The Riddle server is a pretty simple program. While it is running, it waits for
requests to come in and responds when they do. Let's set it up on your Raspberry
Pi.

{{< code-action >}} First clone and install the Riddle server on your personal computer:

```shell
cd /opt
git clone https://github.com/cproctor/riddle_server.git
cd riddle_server
python3 -m venv env
source env/bin/activate
pip install -r requirements.txt
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
