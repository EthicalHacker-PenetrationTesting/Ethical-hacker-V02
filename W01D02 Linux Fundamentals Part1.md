# Linux Fundamentals

## High Level Goals

Welcome to the first part of the "Linux Fundamentals". You're most likely using a Windows or Mac machine, both are different in visual design and how they operate. Just like Windows, iOS and MacOS, Linux is just another operating system and one of the most popular in the world powering smart cars, android devices, supercomputers, home appliances, enterprise servers, and more.

By the end of this lesson, you will be familiar with the following:
1. A Bit of Background on Linux 
2. What is Terminal and running  our first few commands
3. Extract Interacting With the File System
4. Searching for Files
5. Introduction to Shell Operators

## A Bit of Background on Linux

It's fair to say that Linux is a lot more intimidating to approach than Operating System's (OSs) such as Windows. Both variants have their own advantages and disadvantages. For example, Linux is considerably much more lightweight, and you'd be surprised to know that there's a good chance you've used Linux in some form or another every day! Linux powers things such as:

-   Websites that you visit
-   Car entertainment/control panels
-   Point of Sale (PoS) systems such as checkout tills and registers in shops
-   Critical infrastructures such as traffic light controllers or industrial sensors

## What is Terminal and running  our first few commands

The "Terminal" is purely text-based and is intimidating at first. However, if we break down some commands, after some time, you quickly become familiar with using the terminal!

					This is what a terminal looks like
					
	┌──(tetra㉿kali)-[~]
	└─$ enter commands here

We need to be able to do basic functions like navigate to files, output their contents and make files! The commands to do so are self-explanatory.

Let's get started with two of the first commands, which I have broken down in the table below:

| Command | Description  |
|--|--|
| echo | Output any text that we provide |
| whoami | Find out what user we're currently logged in as! |

>  See the snippets below for an example of each command being used...

								Using echo
	
	┌──(tetra㉿kali)-[~]
	└─$ echo Hello World
	 Hello World
	
								using whoami
	┌──(tetra㉿kali)-[~]
	└─$ whoami 
	 tetra


## Extract Interacting With the File System

|Command| Full Name |
|--|--|
|ls | listing |
| cd | change directory |
| cat | concatenate |
| pwd | print working directory |

### Listing Files in Our Current Directory (ls)

Before we can do anything such as finding out the contents of any files or folders, we need to know what exists in the first place. This can be done using the `ls` command (short for listing)

		Using "ls" to to list the contents of the current directory

	┌──(tetra㉿kali)-[~]
	└─$ ls
	'Important Files' 'My Documents' 'Notes' 'Pictures'
	
In the command above, we can see there are the following directories/folders:
-   Important Files
-   My Documents
-   Notes
-   Pictures

> _Pro tip: You can list the contents of a directory without having to navigate to it by using  **ls**  and the name of the directory. I.e.  `ls Pictures`_

### Changing Our Current Directory (cd)

Now that we know what folders exist, we need to use the **`cd`** command (short for **c**hange **d**irectory) to change to that directory. Say, if I wanted to open the "Pictures" directory - I'd do "**cd Pictures**". Where again, we want to find out the contents of this "Pictures" directory and to do so, we'd use **`ls`** again:

								using cd
	┌──(tetra㉿kali)-[~]
	└─$ cd Pictures
	
	┌──(tetra㉿kali)-[~/Pictures]
	└─$ ls
	dog_picture1.jpg dog_picture2.jpg dog_picture3.jpg dog_picture4.jpg
