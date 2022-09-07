---
title: "0. Riddle Server"
type: lab
# draft: true
---

# HTTP: How Computers Communicate

The Internet may be humanity's most profound invention. A global
network of computers talking to one another, making it possible for people all
over the world to interact. In this lab, we will start learning about *how*
computers talk with one another. 

## Vocabulary

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


## [1] The Basic Rules of HTTP
Every time you visit a URL, your computer opens a connection with the server at that address and uses **HTTP** to send and recieve the content. 


## [2] Riddle Server

In this lab we are going to practice getting and sending HTTP requests. Let's begin by using a nice little tool called `httpie`. 

{{< code-action "Install httpie by typing the following into Terminal on your personal computer:" >}}  

```shell
pip3 install httpie
```

{{< code-action "Let's explore the Riddle server by typing the below HTTP request into your terminal." >}} Replace `IP_ADDRESS_GIVEN_BY_TEACHER` with the IP address on the board.

```shell
http GET IP_ADDRESS_GIVEN_BY_TEACHER:5000/riddles/all
```

You should see something like this: 
```shell
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
            "question": "What month of the year has 28 days?"
        }
    ]
}
```

{{< code-action "Do you know the answer? Try posting a guess via the Terminal." >}}

Note that we are now using a different URL, `IP_ADDRESS_GIVEN_BY_TEACHER:5000/riddles/guess`, because we want to guess the answer to a riddle. 

It is common for `POST` requests to send a *payload* with the request. In this case, the payload is a parameter called `id` specifying which riddle we are guessing, as well as `guess`.

```shell
http POST IP_ADDRESS_GIVEN_BY_TEACHER:5000/riddles/guess id=1 guess="All of them"
```

You should see something like this:
```shell
HTTP/1.0 200 OK
Content-Length: 149
Content-Type: application/json
Date: Wed, 09 Sep 2020 21:06:54 GMT
Server: Werkzeug/1.0.1 Python/3.5.2

{
    "correct": true,
    "guess": "All of them",
    "riddle": {
        "correct": 1,
        "guesses": 1,
        "id": 1,
        "question": "What month of the year has 28 days?"
    }
}
```

### [Explore the Endpoints]
Server APIs often rely on different URL *endpoints* to determine what the API should do.

Here is a cheatsheet of the Riddle endpoints, what parameters they take in their payload, and what they do:

| Method | URL                                | Required Payload     | Action                                                                                   |
| ------ | ---------------------------------- | -------------------- | ---------------------------------------------------------------------------------------- |
| `GET`  | `138.68.28.249:5000/riddles/all`   |                      | Returns a list of all the riddles, without answers.                                      |
| `GET`  | `138.68.28.249:5000/riddles/one`   | `id`                 | Returns the riddle if it exists. (Otherwise, it returns an error with status code 404.)  |
| `POST` | `138.68.28.249:5000/riddles/new`   | `question`, `answer` | Creates a new riddle (with an automatically-assigned id). Returns the riddle.            |
| `POST` | `138.68.28.249:5000/riddles/guess` | `id`, `guess`        | Checks whether the guess is correct. In the response, `correct` is `True` or `False`.    |

{{< code-action "Continue to guess riddles and also try adding your own riddles to the server." >}} 

<hr>

### [Host Your Private Riddle Server]

As of now, you've been accessing the riddle server that's hosted on one of the teacher's computers. Let's try hosting the riddle server on your own computer. 

{{< code-action "Clone the riddle server repository into your" >}} `cs10` **folder.**

```shell
git clone https://github.com/cproctor/riddle_server.git
cd riddle_server
pip3 install -r requirements.txt
```

{{< code-action "Run the server." >}} 
```shell
./run.sh
```
 
{{< code-action "Find your IP Address" >}} to access the server and to allow others to access it.The below command will return an IP Address such as `192.168.86.107`.

```shell
ipconfig getifaddr en0
```

{{< code-action "Open a new Terminal window" >}} and access your locally hosted riddle server.

```shell
http GET YOUR_IP_ADDRESS:5000/riddles/all
```

{{< code-action "Create riddles on your own server. Then, share your IP Addresses with your classmates so they can guess." >}} 

{{< checkpoint >}}
Before moving on, answer the following prompts in your notebook:

- What is the difference between a `GET` request and a `POST` request?
- Give an example of when you make a `GET` request in your daily life. 
- Give an example of when you make a `POST` request in your daily life. 
- Why are the riddles not saves across servers? 
{{< /checkpoint >}}

## [3] APIs

{{< code-action "Try visting the Riddle server address" >}}  `IP_ADDRESS_GIVEN_BY_TEACHER:5000/riddles/all` in your web browser. 

You should see something like this:

`{"riddles":[{"correct":1,"guesses":1,"id":1,"question":"What month of the year has 28 days?"}]}`

**Just like with every other website you visit in your browser, to access the Riddle server, your browser sends a `GET` request to the server address. The server resonds with data, and your browser displays it. In this case, the data is all of the riddles in JSON format.**

You might notice that this is not a very pretty or readable representation. That's because the Riddle server is not really meant to be accessed like a webpage. Instead, **the Riddle server is set up as a standalone API (application programming interface)**. APIs are often the backend of applications, and they allow you to interact strictly with the application data without
worrying about the graphical interface. This kind of interface is particularly useful when you are trying to send and
recieve large amounts of data or make many HTTP requests to access similar types of data.

For example, [Wikipedia has an API](https://www.mediawiki.org/wiki/API:Main_page) that let's you access information
about Wikipedia pages without having to go through the graphic interface. If your wanted to see all of the pages that
link to a particular wiki page, going through the graphical interface would be nearly impossible. However, the API
provides an easy way to find this information:

```shell
http GET https://en.wikipedia.org/w/api.php action==query list==backlinks format==json bltitle==Independent_Schools_Foundation_Academy
```

There are lots of [interesting APIs](https://www.twilio.com/blog/cool-apis) that you can use to make some pretty cool projects.

{{< code-action "Explore what APIs the internet has to offer and practice making" >}} `GET` and `POST` **requests.**

