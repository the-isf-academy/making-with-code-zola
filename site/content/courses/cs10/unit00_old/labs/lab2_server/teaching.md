---
title: Teaching the HTTP lab
type: teaching
---

## Troubleshooting

- If the Pis are not on a LAN (or VPN), it will likely be impossible for
  students to connect to each others' Pis. 
- The stock Pi image does not run a firewall by default, but if the Riddle
  server is run on another machine, you will likely need to allow port 5000. 
  For example, on Ubuntu `uwf` is often enabled by default, so you would need to 
  run `sudo ufw allow 5000`.

## If students finish early

The Riddle lab code is challenging, but might be approachable. It's a basic
Flask app, where each view/action is implemented in a function, and a decorator 
maps them to URL routes. Try challenging groups to add a new route, for example
`GET /about` might return some information about whose Riddle server this is.

There is also quite a bit of approachable documentation in `riddle_server/model.py`. 
Some students might be interested in poking around there. 
