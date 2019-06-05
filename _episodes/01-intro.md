---
title: "Introducing The Shell"
teaching: 15
exercises: 5
questions:
 - What is a command shell and why would I use one?
objectives:
 - Explain how the shell relates to the keyboard, the screen, the operating system, and users' programs
 - Explain when and why command-line interfaces should be used instead of graphical interfaces
keypoints:
- "The standard method of interacting with such systems is via a command line interface called Bash."
---


## On Command Line

Using HPC systems often involves the use of a shell through a command line
interface (CLI) and either specialized software or programming techniques.  The
shell is a program with the special role of having the job of running other
programs rather than doing calculations or similar tasks itself.  What the user
types goes into the shell, which then figures out what commands to run and
orders the computer to execute them.  (Note that the shell is called "the
shell" because it encloses the operating system in order to hide some of its
complexity and make it simpler to interact with.)  The most popular Unix shell
is Bash, the Bourne Again SHell (so-called because it's derived from a shell
written by Stephen Bourne).  Bash is the default shell on most modern
implementations of Unix and in most packages that provide Unix-like tools for
Windows.

Interacting with the shell is done via a command line interface (CLI) on most
HPC systems.  In the earliest days of computers, the only way to interact with
early computers was to rewire them.  From the 1950s to the 1980s most people
used line printers.  These devices only allowed input and output of the
letters, numbers, and punctuation found on a standard keyboard, so programming
languages and software interfaces had to be designed around that constraint and
text-based interfaces were the way to do this.  Typing-based interfaces are
often called a **command-line interface**, or CLI, to distinguish it from a
**graphical user interface**, or GUI, which most people now use.  The heart of
a CLI is a **read-evaluate-print loop**, or REPL: when the user types a command
and then presses the Enter (or Return) key, the computer reads it, executes it,
and prints its output.  The user then types another command, and so on until
the user logs off.

Learning to use Bash or any other shell sometimes feels more like programming
than like using a mouse.  Commands are terse (often only a couple of characters
long), their names are frequently cryptic, and their output is lines of text
rather than something visual like a graph.  However, using a command line
interface can be extremely powerful, and learning how to use one will allow
you to reap the benefits described above.  

## The rest of this lesson

The only way to use these types of resources is by learning to use the command line.
This introduction to HPC systems has two parts:

* We will learn to use the UNIX command line (also known as Bash).
* We will use our new Bash skills to connect to and operate a high-performance computing supercomputer.

The skills we learn here have other uses beyond just HPC -
Bash and UNIX skills used everywhere, be it for web development, running software, or operating servers.
It's become so essential that Microsoft
[now ships it as part of Windows](https://www.microsoft.com/en-us/store/p/ubuntu/9nblggh4msv6)!
Knowing how to use Bash and HPC systems will allow you to operate virtually any modern device.
Wit all of this in mind, let's connect to a cluster and get started!
