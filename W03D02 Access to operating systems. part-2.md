# Access to operating systems

# Client side

## High Level Goals

By the end of this lesson, you will be familiar with the following:
1. Installing & Running Veil
2. Payloads overview
3. Generating a Veil backdoor
4. Listening for connection 

## Installing & Running Veil

First things we want to run Kali and Window 10,  we will use **Veil - Framework**.

We can use it by following this steps:

1. Go to the terminal and write, `rm -rf /root/.config/wine/vei` 
2. In the terminal write cd `cd /usr/share/veil/config`
3. Then write `./setup.py --force --silent`
4. Finally, `cd ..` and write `./Veil.py`

![Veil1](/img/Veil1.png)


What is Veil?

The Veil Framework is a collection of tools designed for use during offensive security testing. When the time calls for it, Mandiant’s Red Team will use the Veil-Framework to help achieve their objective.  The most commonly used tool is Veil-Evasion, which can turn an arbitrary script or piece of shell code into a Windows executable that will evade detections by common antivirus products.

The `list` command displays Veil's main commands, which are as follows:

1. **Evasion**: This generates undetectable backdoors.
2. **Ordnance**: This generates the payloads used by Evasion; this is more of a
secondary tool.

## Payloads overview

Let's use **Evasion** by typing `use 1` 

![Veil2](/img/Veil2.png)

As we can see Veil gives a list of commands that can run on this tool, let's write `list` to give us all available payloads 

![Veil3](/img/Veil3.png)

The first part of the payload's name is `cs`, which refers to the programming
language the payload will be wrapped in. As you can see in the preceding
screenshot, languages used include GO, C, CS, Python, PowerShell, and Ruby.

The second part of any payload is really important, as this is the type of payload;
in other words, the type of code that's going to be executed on the target
computer.

we will use `15) go/meterpreter/rev_https.py` 

In this example, we're using Meterpreter, which is a payload designed by Metasploit.

### What is Meterpreter?
Meterpreter is an advanced, dynamically extensible payload that uses _in-memory_ DLL injection stagers and is extended over the network at runtime. It communicates over the stager socket and provides a comprehensive client-side Ruby API. It features command history, tab completion, channels, and more.

The third part of a payload's name is the method that's going to be used to
establish its connection. In our example, that's rev_https. rev, which stands for
reverse, and https is the protocol that will be used to establish the connection.
There are also a few examples of rev_tcp in the preceding screenshot, which
creates a reverse TCP connection.
