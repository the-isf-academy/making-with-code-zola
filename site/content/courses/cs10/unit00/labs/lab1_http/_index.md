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

Every time you visit a URL, your computer opens a connection with the server at that address and uses **HTTP Protocol** to recieve the content. For example, by visiting "cs.fablearn.org" you initiate a **GET Request** to recieve the *Making with Code* homepage from the server. 

A **GET Request** contains following: 

```shell
GET / HTTP/1.1
Host: cs.fablearn.org
```

Another frequently utilized request is a **POST request**. A `POST` Request is sent when you are sending data to the server. For example, logging into an account or making an online purchase. 

In the **POST Request** below, the webpage would contain a form to recieve the user's data. 

```shell
POST / HTTP/1.1
Host: social_media_login.com
```

Once the request has been recieved by the server, it responds by sending the client a **HTTP Response Status Code**. If a successful connection has been made, the server sends the content to the client. 

A successful **HTTP Status Code** contains the following:

```shell
HTTP/1.1 200 OK
Content-Type: text/html
```

The `Content-Type` tells your computer what type of data is being recieved. For "cs.fablearn.org", your computer recieves the HTML, Javacsript, CSS, and image files that make up the homepage of the site. 

{{<expand "Common HTTP Status Codes" >}}
- `200` means success.
- `300` means you're looking in the wrong place
- `400` means you did something wrong.
- `404` means the resource requested could not be found 
- `500` means, "Sorry, the server broke!" 

{{</expand>}}


{{< code-action >}} To see status codes in action:

0. Right click on any website and click "Inspect"
0. Select "Network" from the top tool bar in the devleoper tools
0. Hard refresh your page with "Command + Shift + R"
0. Find the URL under "Name"
0. Under the "Status" column you will see "200", signifiying a sucessful **GET** request


{{< aside >}}
**All actions on the Internet are composed of HTTP Requests.** 

 - Every time you access a website, it triggers a series of HTTP Requests depending on its complexity. 
 - Every time a client requests information from a server, the request is recorded along with the status code.

{{<expand "An Analogy to better understand HTTP Requests" >}}
It can be tricky to understand how HTTP functions because it’s difficult to examine what your browser is actually doing. (And perhaps also because we explained it using acronyms that may be new to you.) Let’s review what we learned by using an analogy that could be more familiar to you.

Imagine the internet is a town. You are a client and your address determines where you can be reached. Businesses in town, such as Codecademy.com, serve requests that are sent to them. The other houses are filled with other clients like you that are making requests and expecting responses from these businesses in town. This town also has a crazy fast mail service, an army of mail delivery staff that can travel on trains that move at the speed of light.

Suppose you want to read the morning newspaper. In order to retrieve it, you write down what you need in a language called HTTP and ask your local mail delivery staff agent to retrieve it from a specific business. The mail delivery person agrees and builds a railroad track (connection) between your house and the business nearly instantly, and rides the train car labeled “TCP” to the address of the business you provided.

Upon arriving at the business, she asks the first of several free employees ready to fulfill the request. The employee searches for the page of the newspaper that you requested but cannot find it and communicates that back to the mail delivery person.

The mail delivery person returns on the light speed train, ripping up the tracks on the way back, and tells you that there was a problem “404 Not Found.” After you check the spelling of what you had written, you realize that you misspelled the newspaper title. You correct it and provide the corrected title to the mail delivery person.

This time the mail delivery person is able to retrieve it from the business. You can now read your newspaper in peace until you decide you want to read the next page, at which point, you would make another request and give it to the mail delivery person.

*Source: [https://www.codecademy.com/articles/http-requests](https://www.codecademy.com/articles/http-requests)*

{{</expand>}}

{{< /aside >}}

<br>

## Let's try it

In this lab we are going to practice getting and sending HTTP requests. Let's begin by using a
nice little tool called `httpie`. 

{{< code-action >}}  Let's install it:

```shell
$ pip3 install httpie
```

{{< code-action >}} There is a Riddle server running at `138.68.28.249:5000`. Let's see
which riddles are available for guessing by entering the following into your terminal:

```shell
$ http GET 138.68.28.249:5000
```

{{< code-action >}} Do you know the answer to any of the riddles? Try guessing the answer to a riddle by sending a **POST** request and using the following format:

```shell
$ http POST 138.68.28.249:5000/1 guess="A banana"
```

The URL is now `138.68.28.249:5000/1` because we are guessing riddle #1. It is common for POST requests to send a payload with the request. In this case, the payload is a
parameter called `guess`.

Each POST request will return text in the following format:

```shell
HTTP/1.0 200 OK
Content-Length: 149
Content-Type: application/json
Date: Wed, 09 Sep 2020 08:30:41 GMT
Server: Werkzeug/1.0.1 Python/3.5.2

{
    "correct": false,
    "guess": "pizza",
    "riddle": {
        "correct": 2,
        "guesses": 10,
        "id": 4,
        "question": "I'm tall when I'm young and short when I'm old. What am I?"
    }
}
```

{{< code-action >}} Continue to guess riddles and also try adding your own riddle 
to the server. 

The [riddle documentation](https://github.com/cproctor/riddle_server) will help here, but here 
is a cheatsheet of all the URL routes:

| Method | URL                    | Action                                                                                               |
| ------ | ---------------------- | ---------------------------------------------------------------------------------------------------- |
| `GET`  | `138.68.28.249:5000/`  | Returns a list of all the riddles, without answers.                                                  |
| `GET`  | `138.68.28.249:5000/x` | Returns the riddle with id `x` if it exists. (Otherwise, it returns an error with status code 404.)  |
| `POST` | `138.68.28.249:5000/`  | Creates a new riddle if `question` and `answer` are provided. The new riddle is returned.            |
| `POST` | `138.68.28.249:5000/x` | Accepts a `guess` for riddle `x` if it exists. The response says whether you were correct. |

{{< checkpoint >}}

Once you have successfully posted a riddle to the server, draw a model that illustrates the process of accessing the riddle server and its functionality. 

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
