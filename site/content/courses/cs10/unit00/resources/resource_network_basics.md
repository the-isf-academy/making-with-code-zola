---
title: "Network Basics"
type: resource
---

{{< tabs networking >}}

{{< tab "Text Eplanation" >}}
You are probably most familiar with your wifi router because it offers your computer access to the internet. In this case, your
computer connects to the router's wifi network and begins sending messages to the router. The wifi router recieves these messages
and forwards them to the appropriate place via the internet.

For example, if you click [this link](https://en.wikipedia.org/wiki/ARPANET),
your computer will send a request to your wifi router to return the content of the page at the URL. Your router will recieve this
message and forward it to one of Wikipedia's servers somewhere in the world. When the Wikipedia server recieves the message, it
reads it, packages up the content of the page at the URL, and sends the content back to your router. Your router then forwards this
reply to your computer which interprets the content and displays it in your web browser.

{{< figure src="images/courses/cs10/unit00/00_fresh_internet.png" width="100%" title="Connecting to the internet via wifi" >}}

This is obviously an extremely useful feature of your wifi router. You probably use it every day! However, we're going to use another
feature of your wifi router that you may not have used before.

Generally, wifi routers create local area networks (LAN) that create a wireless interface between all the devices connected to
the router. For example, if you have a wifi-enabled speaker or printer, your wifi router is probably making the connection between
your computer (or phone) and the device. When you want to print something, your computer sends a message to your wifi router containing
the file it wants to print. However, rather than being addressed to a destination at a server somewhere far away, this message is addressed
to your printer. Your wifi router notices this and forwards the message to your printer through the LAN. When the printer recieves
the message, it interprets it and prints the file. Your communication never left the local network created by your wifi router.

{{< figure src="images/courses/cs10/unit00/00_fresh_lan.png" width="100%" title="Connecting to another deivce over a LAN" >}}
{{< /tab >}}

{{< tab "Video Explanation" >}}

{{< youtube id="7_LPdttKXPc" >}}

{{< /tab >}}
{{< /tabs >}}
