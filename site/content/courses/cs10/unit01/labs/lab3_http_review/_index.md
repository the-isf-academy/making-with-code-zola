---
title: 2. HTTP Review

draft: true
---

# HTTP Review

Welcome back from break! Let's start by doing a review of how to make HTTP `GET` and HTTP `POST` requests.

## Email Directory

The teaching team has created a `cs10-email-directory` server:<br> [https://cs10-email-directory.herokuapp.com](https://cs10-email-directory.herokuapp.com).

{{< code-action "Let's explore the server by typing the below HTTP request into your terminal." >}}
```shell
http get https://cs10-email-directory.herokuapp.com/
```

You should see the following output:
```shell
HTTP/1.1 200 OK
Connection: keep-alive
Content-Length: 49
Content-Type: application/json
Date: Sun, 02 Jan 2022 13:39:31 GMT
Referrer-Policy: same-origin
Server: gunicorn
Via: 1.1 vegur
X-Content-Type-Options: nosniff
X-Frame-Options: DENY

{
    "index": "Welcome to the CS10 Email Directory!"
}

```


{{< code-action "Using the chart below, make an HTTP request to each endpoint." >}}


| HTTP Request | Endpoint     | Payload                             |
|--------------|--------------|-------------------------------------|
| GET          | /            | none                                |
| GET          | /all_persons | none                                |
| GET          | /one_person  | name: string                        |
| POST         | /add_person  | name: string, email_address: string |

{{< expand "Making HTTP Requests with a Payload" >}}



To learn more, reference the httpie [documentation](https://httpie.io/docs/cli/request-url)
{{< /expand >}}

```shell
http get example.com name=name
```

### API View

You can also make HTTP requests to the server via the API view:
[https://cs10-email-directory.herokuapp.com/api](https://cs10-email-directory.herokuapp.com/api).

{{< code-action "Now, make HTTP requests using the API interface." >}}


