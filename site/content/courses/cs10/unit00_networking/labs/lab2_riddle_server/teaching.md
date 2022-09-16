---
title: Teaching the HTTP lab
type: teaching
---

## Setup

Before teaching the lab, you will need to deploy the Riddle server on some
publicly-accessible machine, and update the lab with its URL. Instructions are
provided in [the Riddle server README](https://github.com/cproctor/riddle_server).
(The simplest way to deploy this is to ssh into the server machine, clone the
repo, install dependencies, and then run `run.sh` in a tmux or screen session so
you can detach it and leave it running. 

## Troubleshooting

### Hardware

- If the Pis are not on a LAN (or VPN), it will likely be impossible for
  students to connect to each others' Pis. 
- The stock Pi image does not run a firewall by default, but if the Riddle
  server is run on another machine, you will likely need to allow port 5000. 
  For example, on Ubuntu `uwf` is often enabled by default, so you would need to 
  run `sudo ufw allow 5000`.

### Software

- When students are implementing the client api, they need to use
  `requests.get(url, json=payload)`, not `requests.get(url, data=payload)`.
  Using the `json` keyword argument will ensure the payload is sent as JSON, not
  form-encoded (which the server will reject). The code examples provided in
  `api.py` correctly use `json`, but `data` is more prominent in the `requests`
  documentation.
