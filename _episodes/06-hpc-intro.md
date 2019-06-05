---
title: "Why Use a Cluster?"
teaching: 15
exercises: 5
questions:
- "Why would I be interested in High Performance Computing (HPC)?"
- "How do I connect to a remote computer?"
objectives:
- "Be able to describe what an HPC system is"
- "Identify how an HPC system could benefit you."
- "Connect to a cluster."
keypoints:
- "High Performance Computing (HPC) typically involves connecting to very large computing systems elsewhere in the world."
- "These other systems can be used to do work that would either be impossible or much slower on smaller systems."
- "To connect to a cluster using SSH: `ssh yourUsername@remote.computer.address`"

---

## Why Use These Computers?

> ## What do you need?  
>
> Talk to your neighbor about your research.  How does computing
> help you do your research?  How could more computing help you
> do more or better research?  
{: .challenge}

Frequently, research problems that use computing can outgrow the desktop
or laptop computer where they started:

* A statistics student wants to do cross-validate their model.  This involves
running the model 1000 times -- but each run takes an hour.  Running on their
laptop will take over a month!

* A genomics researcher has been using small datasets of sequence data, but
soon will be receiving a new type of sequencing data that is 10 times as large.
It's already challenging to open the datasets on their computer -- analyzing
these larger datasets will probably crash it.

* An engineer is using a fluid dynamics package that has an option to run
in parallel.  So far, they haven't used this option on their desktop, but in
going from 2D to 3D simulations, simulation time has more than tripled and it
might be useful to take advantage of that feature.  

In all these cases, what is needed is access to more computers than can be
used at the same time.  Luckily, large scale computing systems -- shared computing
resources with lots of computers -- are available at many universities, labs,
or through national networks.  These resources usually have
more central processing units(CPUs), CPUs that operate at higher speeds,
more memory, more storage, and
faster connections with other computer systems.  They are frequently called
"clusters", "supercomputers" or resources for "high performance computing" or
HPC.  In this lesson, we will usually use the terminology of HPC and HPC cluster.  

Using a cluster often has the following advantages for researchers:

* **Speed.** With many more CPU cores, often with higher performance specs,
  than a typical laptop or desktop, HPC systems can offer
  significant speed up.
* **Volume.** Many HPC systems have both the processing memory (RAM) and disk
  storage to handle very large amounts of data. Terabytes of RAM and
  petabytes of storage are available for research projects.
* **Efficiency.** Many HPC systems operate a pool of resources that are drawn
  on by a many users.  In most cases when the pool is large and diverse enough
  the resources on the system are used almost constantly.
* **Cost.** Bulk purchasing and government funding mean that the cost to the
  research community for using these systems in significantly less that it
  would be otherwise.
* **Convenience.** Maybe your calculations just take a long time to run or are
  otherwise inconvenient to run on your personal computer. There's no need to
  tie up your own computer for hours when you can use someone else's instead.

This is how a large-scale compute system like a cluster can help solve problems like
those listed at the start of the lesson.  

> ## Thinking ahead
>
> How do you think using a large-scale computing system will be different
> from using your laptop? Talk to your neighbor about some
> differences you may already know about, and some
> differences/difficulties you imagine you may run into.
{: .challenge}

## Opening a Terminal

We used a terminal application on our laptops this morning to learn
how to use Linux shell commands on our laptops.

We will now see how to use Linux shell commands on a remote computer.  Connecting to a remove Linux computer is most often done through a tool known as "SSH"
(Secure SHell) and usually SSH is run through a terminal.  We will now briefly review the available terminal applications and how to use them for an ssh connection.

### Linux

There are many different versions (aka "flavours") of Linux and how to open a
terminal window can change between flavours. Fortunately most Linux users
already know how to open a terminal window since it is a common part of the
workflow for Linux users. If this is something that you do not know how to do
then a quick search on the Internet for "how to open a terminal window in"
with your particular Linux flavour appended to the end should quickly give
you the directions you need.

A very popular version of Linux is Ubuntu. There are many ways to open a
terminal window in Ubuntu but a very fast way is to use the terminal shortcut
key sequence: Ctrl+Alt+T.

### Mac

Macs have had a terminal built in since the first version of OSX since it is
built on a Linux flavour known as BSD (Berkeley Systems Designs). 
The terminal can be quickly opened through the use of the Searchlight tool. 
Hold down the command key and press the spacebar. 
In the search bar that shows up type "terminal", choose the terminal app from the list of results (it will
look like a tiny, black computer screen) and you will be presented with a terminal window.
Alternatively, you can find Terminal under "Utilities" in the Applications menu.

### Windows

#### MobaXterm

We saw MobaXterm this morning, which is a terminal window emulator for
Windows available at
[mobatek.net](https://mobaxterm.mobatek.net/download-home-edition.html).

Once the MobaXterm window is open you should see a large button in the middle
of that window with the text "Start Local Terminal". Click this button and
you will have a terminal window at your disposal.

#### PuTTY

It is strictly speaking not necessary to have a terminal running on your local computer in order to access and use a remote system, only a window into the remote system once connected.  PuTTy is likely the oldest, most well-known, and widely used software solution to take this approach.

PuTTY is available for free download from [www.putty.org](http://www.putty.org/).  Download the version that is correct for your operating system and install it as you would other software on you Windows system.  Once installed it will be available through the start menu or similar.

Running PuTTY will not initially produce a terminal but instead a window full of connection options.  Putting the address of the remote system in the "Host Name (or IP Address)" box and either pressing enter or clicking the "Open" button should begin the connection process.

If this works you will see a terminal window open that prompts you for a username through the "login as:" prompt and then for a password.  If both of these are passed correctly then you will be given access to the system and will see a message saying so within the terminal.  If you need to escape the authentication process you can hold the control/ctrl key and press the c key to exit and start again.

Note that you may want to paste in your password rather than typing it.  Use control/ctrl plus a right-click of the mouse to paste content from the clipboard to the PuTTY terminal.

For those logging in with PuTTY it would likely be best to cover the terminal basics already mentioned above before moving on to navigating the remote system.

## Logging onto the system

With all of this in mind, let's connect to a cluster. 
For these examples, we will connect to Graham - a high-performance cluster located at the University of Waterloo.
Although it's unlikely that every system will be exactly like Graham, 
it's a very good example of what you can expect from a supercomputing installation.
To connect to our example computer, we will use SSH (if you are using PuTTY, see above). 

SSH allows us to connect to UNIX computers remotely, and use them as if they were our own.
The general syntax of the connection command follows the format `ssh yourUsername@some.computer.address`
Let's attempt to connect to the cluster now:

```
ssh yourUsername@graham.computecanada.ca
```
{: .bash}

```{.output}
The authenticity of host 'graham.computecanada.ca (199.241.166.2)' can't be established.
ECDSA key fingerprint is SHA256:JRj286Pkqh6aeO5zx1QUkS8un5fpcapmezusceSGhok.
ECDSA key fingerprint is MD5:99:59:db:b1:3f:18:d0:2c:49:4e:c2:74:86:ac:f7:c6.
Are you sure you want to continue connecting (yes/no)?  # type "yes"!
Warning: Permanently added the ECDSA host key for IP address '199.241.166.2' to the list of known hosts.
yourUsername@graham.computecanada.ca's password:  # no text appears as you enter your password
Last login: Wed Jun 28 16:16:20 2017 from s2.n59.queensu.ca

Welcome to the ComputeCanada/SHARCNET cluster Graham.
```

If you've connected successfully, you should see a prompt like the one below. 
This prompt is informative, and lets you grasp certain information at a glance:
in this case `[yourUsername@computerName workingDirectory]$`.
(If you don't understand what these things are, don't worry! 
We will cover things in depth as we explore the system further.)

```{.output}
[yourUsername@gra-login1 ~]$
```

## Telling the Difference between the Local Terminal and the Remote Terminal

You may have noticed that the prompt changed when you logged into the remote
system using the terminal (if you logged in using PuTTY this will not apply
because it does not offer a local terminal). This change is important because
it makes it clear on which system the commands you type will be run when you
pass them into the terminal. This change is also a small complication that we
will need to navigate throughout the workshop. Exactly what is reported
before the `$` in the terminal when it is connected to the local system and
the remote system will typically be different for every user. We still need
to indicate which system we are entering commands on though so we will adopt
the following convention:

`[local]$` when the command is to be entered on a terminal connected to your local computer

`[remote]$` when the command is to be entered on a terminal connected to the remote system

`$` when it really doesn't matter which system the terminal is connected to.

> ## Being Certain Which System your Terminal is connected to
> If you ever need to be certain which system a terminal you are using is connected to 
> then use the follwing command: `$ hostname`.
{: .callout}

> ## Keep Two Terminal Windows Open
> It is strongly recommended that you have two terminals open, one connected
> to the local system and one connected to the remote system, that you can
> switch back and forth between. If you only use one terminal window then you
> will need to reconnect to the remote system using one of the methods above
> when you see a change from `[local]$` to `[remote]$` and disconnect when you
> see the reverse.
{: .callout}
