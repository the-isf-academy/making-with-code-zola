---
title: Initial Setup
numberHeaders: true
weight: -1
---

# Initial setup

Welcome! These instructions will help you get your computer set up for the class.
If you get stuck or are unsure what to do, ask {{< teacher >}}. Everyone's system is 
different, so the initial setup sometimes needs some TLC. 
You should only ever have to run these instructions once. 

## The basics
To get your computer ready, we need to configure the workspace you will use for the class. Select the tab for your operating system and follow the instructions. Please let {{< teacher >}} know if you run into any issues. 


{{< tabs "computer-setup" >}}
{{< tab "MacOS" >}}

Start by installing the latest version of Python. [Open this link](https://www.python.org/downloads/), 
click "Download Python," and follow the installation instructions.

Once the installation finishes, you will see a Finder window showing what was installed. 
(If you closed the window, open Finder, click on "Applications," and then "Python 3.10" (or whatever
version of Python you just installed).

Double-click on "Install Certificates.command" and then 
"Update Shell Profile.command". Each of these will open a Terimal window and run a bunch of commands. 
Once you see `[Process completed]`, you may close the window.

{{< aside >}}
If you see a red "Permission denied" error message when running "Install Certificates.command", open a 
Terminal window and run `sudo "/Applications/Python 3.10/Install Certificates.command"` instead. You will be asked 
for an administrator password; you won't see any letters appearing as you enter the password. This is a security feature.
{{</ aside >}}

{{< /tab >}}

{{< tab "Windows" >}}
### 💻 Check system requirements 

1. Go to `Settings > System > About`.
1. Check that the Edition is Windows 10.
1. Check that System type says "64-bit operating system..."

*(based on [this guide](https://www.howtogeek.com/228042/how-to-switch-from-32-bit-windows-10-to-64-bit-windows-10/))*

### 💻 Ubunutu 
Follow along with this video until the '6:15' mark, or follow the steps below. Once you have Ubunutu installed, skip below to "Download VcXsrv for graphics". 

{{< youtube "1ap3hL-UR9I" >}}

#### Enable developer tools
1. Go to `Control Panel > Programs > Program Features > Turn Windows Features On Or Off`.
1. Enable the “Windows Subsystem for Linux” option in the list, and then click the “OK” button.
1. Click “Restart now” when you’re prompted to restart your computer.

#### Download Ubuntu
1. After your computer restarts, open the Microsoft Store from the Start menu, and search for
“Ubunutu” in the store. 
1. Click `Get` to install "Ubuntu".

*(Based on [this guide](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/))*

#### Setup Ubuntu
1. Open Ubuntu, it will take a few minutes to install updates.
1. As prompted, create a username and password.
1. Give your user admin privileges by typing `usermad -aG sudo your-name` and pressing enter
   (again, replace `your-name`).
1. Run the following commands:

```shell
sudo apt update && upgrade
sudo apt install python3 python3-pip
```

### 💻Download VcXsrv for graphics
1. Download VcXsrv from [this link](https://www.onworks.net/software/windows/app-vcxsrv-windows-x-server) by clicking `Download App`. 
1. Install the package that downloads by double clicking on it and going through the install wizard.

### 💻Download Atom
1. Download Atom from [this website](https://atom.io/) and install.

([This guide](https://medium.com/@rhdzmota/python-development-on-the-windows-subsystem-for-linux-wsl-17a0fa1839d)
has instructions for installing shell commands to open files and projects in Atom)

{{< aside >}}
Whenever this website says to use Terminal, you should use Ubuntu. There will be other small differences
for Windows users that we'll explain along the way.
{{< /aside >}}
{{< /tab >}}
{{< /tabs >}}

## Install MWC

{{< code-action "Open Terminal and run the following command." >}}
`mwc` is a special program we wrote for this class which will help you set up your assignments.

```shell
pip3 install making-with-code-cli
```
{{< aside >}}
If this doesn’t work, try running `sudo pip3 install making-with-code-cli` or `pip3 install --user making-with-code-cli`. Still no luck? Talk to {{< teacher >}}. 
{{</ aside >}}

## Configure MWC

{{< code-action "Run the following command." >}}
You will be asked some questions to finish the setup process. A few notes:
- We suggest accepting default values for now. You can change your settings later by re-running 
  `mwc setup`.
- You'll be asked for the Making With Code URL. That's this site, `{{< baseurl >}}`.
- When you are asked for your computer password, you won't see any letters appear as you type. 
  This is normal--it's to keep the person standing behind you from seeing your password.

```shell
mwc setup
```

{{< checkpoint >}}
Congratuations! You're finished. We won't continue until everyone gets set up. Can you help 
someone else?
{{</checkpoint >}}
