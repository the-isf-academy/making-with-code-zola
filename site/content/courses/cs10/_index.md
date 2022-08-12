---
title: CS10
type: course
slug: cs10
git_backend: github
#git_backend: github_organization
---

## Calendar

{{< gdocs src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRPxZAyxM6GXY0wJlvTGb5RKavn3UbWtt4WQDX6Yo4L_XoR5S5taCnaQA2ZVhFD3BZIEGg4QHk6SHXk/pubhtml?widget=true&amp;headers=false" >}}

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
  new technical and programatic ideas.
- Checkups provide brief individual practice of content explored in labs.
- Projects are individual opportunities to apply and extend content.
- Problem sets are non-programming work consisting of proofs, discrete math, and
  other analysis core to CS which is not programming. 

## New structure: Raspberry Pi

Each student will have a Raspberry Pi as a computing companion this year. These will be used in each
unit, and will also ease some of the difficulties of remote teaching. 

### Hardware

The Pi's will run a pre-configured image which reduces headaches to the maximum extent possible.
This features a config scripts which setups up a Linux user and connects to the student's
home wifi network. 

RPis will be configured to connect to a school-provided VPN, so that they can easily 
interact with one another over a LAN and to minimize the risk of malware or data exposure.
Keeping them on a VPN also allows teachers to remotely access the devices for debugging.
The VPN will provide internet access for services like GitHub, but it could be 
severely filtered. 

Any time the RPi cannot find a wifi network to access, it will go into broadcast mode,
broadcasting a wifi network to which students can connect from their laptops. 
