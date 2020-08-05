---
title: CS10
type: course
---

This is Chris Proctor's proposal for CS10. The overall goals of CS10 are to:

- Continue with the pedagogical approach of CS9
- Build on the concepts and practices we develped in CS9
- Layer in more challenging programming and rigorous computational thinking
- Serve as a bridge between the open-ended invitation that was CS9 and the
  demands of IB CS which students will face in grades 11 and 12. 

## Curriculum

{{< expand "Unit 0: Networking" >}}

Perhaps even more than through computational power, computers have transformed our lives through networking. This unit explores how computers interact with each other and will give us opportunities to think about the behavior of larger systems, including how our lives are touched by computer networks. 
{{< /expand >}}

{{< expand "Unit 1: Hardware" >}}
This unit will focus on how inanimate matter can be put to work doing
computation. We will learn some basics of how operating systems interact with
bare metal, how computers can interact with physical sensors and actuators (via
RPi's GPIO), as well as how communication works between computers, using 
ESP8266/32 chips. In this unit we will also read and write speculative fiction exploring the
social future of computing hardware and embodiment. 
{{< /expand >}}

{{< expand "Unit 2: Entrepreneurship" >}}
This unit will consider what students can actually do with computers, and will
serve as a capstone of the two-year sequence. Students will develop a hardware
or software product designed either to be profitable or to solve a social
problem. All projects must involve interaction with real-world potential
clients. The unit will address human-computer interaction and design and prototyping
methodologies, including the use of logging and analytics for quantitative user
research. 
{{< /expand >}}

## New structure: Problem Sets

{{< devnote >}}
Move this over to practices/activity/problem_sets, and generally clean up that
area.
In addition to labs, homework, and projects, we will also now add problem sets.
{{< /devnote >}}

- Labs are collaborative discovery sessions introducing students to
  new ideas.
- Homework is individual practice of content explored in labs.
- Projects are individual opportunities to apply and extend content.
- Problem sets are non-programming work consisting of proofs, discrete math, and
  other analysis core to CS which is not programming. 

## New structure: Raspberry Pi

Each student will have a Raspberry Pi as a computing companion this year. These will be used in each
unit, and will also ease some of the difficulties of remote teaching. 

### Hardware

With a router, we could stand up a little local-area network without the fussing of modern security protections on MacOS and Windows. This would let us write networked apps, learn about IP addresses, ssh, etc. We could also use them later in the year for GPIO control of hardware. And there's a huge learning ecosystem for RPi so folks who want to go further could.

One thing we would need to do would be to create a pre-configured image which reduces headaches to the maximum extent possible. OR, maybe more robust, we should create a config script. One thing I'd propose is having an invoke-based course tools repo which, among other things, can configure and check the image, and can report back to home base on the state of the pi for assessment and debugging. In the case that we had to go remote again, we could use a VPN to get all the Pis back onto the same local area network.


1. RPis should be configured to connect to a school-provided VPN, so that they can easily interact with one another over a LAN and to minimize the risk of malware or data exposure. Keeping them on a VPN also allows teachers to remotely access the devices for debugging. The VPN will need to provide internet access for services like GitHub, but it could be severely filtered. 

2. Create an image which can be flashed onto the rpi if students have trouble. 
  - It should have VPN credentials and configuration baked in. [OpenVPN](https://www.ovpn.com/en/guides/raspberry-pi-raspbian) is a good option for a raspi client.
  We could even host the VPN on a raspi using [this guide](https://www.pcmag.com/how-to/how-to-create-a-vpn-server-with-raspberry-pi)
  - It should have a teacher user baked in, with ssh access and teachers' public keys. Linux user documentation [here](https://www.raspberrypi.org/documentation/linux/usage/users.md).
  - On login, it should prompt the user for required config. This includes username, password, school ID, github username, and local wifi credentials. Details of the files the config script will edit are documented [here](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md).
  - Any time the RPi cannot find a wifi network to access, it should go into broadcast mode, broadcasting a wifi network to which students can connect from their laptops. [This script](https://www.raspberryconnect.com/projects/65-raspberrypi-hotspot-accesspoints/157-raspberry-pi-auto-wifi-hotspot-switch-internet) should do the trick. 
  - As much as possible, services should be distributed via PyPI or aptitude so that we don't have to re-release the image.
  - An alternative approach could be to use [PiServer](https://www.raspberrypi.org/blog/piserver/) to centrally
  manage the Pis. This could be useful if students break their Pis because everything is stored in a central
  server Pi. However, not sure if this service can be accessed over a VPN.

3. Creating a sense of embodiment, copresence, and geographic space. 
  - Provide tools for network and port scanning to show real-time whose pi is online, and which ports respond. 
  - Write flask-based servers for various projects in which students serve simple projects over various ports. Self-hosted personal websites. 
  - Consider using the [Sense Hat](https://www.deviceplus.com/raspberry-pi/raspberry-pi-sense-hat-led/) or some other GPIO pixel array to have each student broadcast status via a single pixel to all other boards. 

