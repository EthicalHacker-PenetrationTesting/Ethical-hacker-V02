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

### Outputting the Contents of a File (cat)

While knowing about the existence of files is great — it's not all that useful unless we're able to view the contents of them.

We will come on to discuss some tools available to us that allows us to transfer files from one machine to another in a later lesson. But for now, we're going to talk about simply seeing the contents of text files using a command called **`cat`**.

**Cat** is short for concatenating & is a fantastic way for us to output the contents of files (not just text files!).

In the command below, you can see how I have combined the use of "ls" to list the files within a directory called "Documents":
	
	┌──(tetra㉿kali)-[~/Documents]
	└─$ ls
	todo.txt
	
	┌──(tetra㉿kali)-[~/Documents]
	└─$ cat todo.txt
	Here's something important for me to do later!

We've applied some knowledge from earlier in this section to do the following:

1.  Used **`ls`** to let us know what files are available in the "Documents" folder of this machine. In this case, it is called "todo.txt".
2. We have then used `cat todo.txt` to concatenate/output the contents of this "todo.txt" file, where the contents are "Here's something important for me to do later

> _Pro tip: You can use  `cat`  to output the contents of a file within directories without having to navigate to it by using  **cat** and the name of the directory. I.e.  `cat /home/ubuntu/Documents/todo.txt`_

### Finding out the full Path to our Current Working Directory (pwd)

It's easy to lose track of where we are on the file system exactly, which is why I want to introduce **`pwd`**. This stands for  **p**rint  **w**orking  **d**irectory.

Using the example machine from before, we are currently in the "Documents" folder — but where is this exactly on the Linux machine's filesystem? We can find this out using this "pwd" command, like within the command below:

	┌──(tetra㉿kali)-[~/Documents]
	└─$ pwd
	/home/tetra/Documents
	
	┌──(tetra㉿kali)-[~/Documents]
	└─$ 
**Let's break this down:**
1.  We already know we're in "Documents" thanks to our terminal, but at this point in time, we have no idea where "Documents" is stored so that we can get back to it easily in the future.
2.  I have used the **`pwd`** (**p**rint  **w**orking  **d**irectory) command to find the full file path of this "Documents" folder.
3.  We're helpfully told by Linux that this "Documents" directory is stored at "/home/tetra/Documents" on the machine — great to know!
4.  Now in the future, if we find ourselves in a different location, we can just use  `cd /home/tetra/Documents`  to change our working directory to this "Documents" directory.

## Searching for Files

One fantastic way to show just how efficient you can be with systems like this is using a set of commands to quickly search for files across the entire system that our user has access to. No need to consistently use `cd` and `ls` to find out what is where. Instead, we can use commands such as `find` to automate things like this for us!

This is where Linux starts to become a bit more intimidating to approach -- but we'll break this down and ease you into it.

### **Using Find**

Take the snippet below, we can see a list of directories available to us:

	┌──(tetra㉿kali)-[~]
	└─$ ls
	Desktop Documents Pictuers folder1
	
	┌──(tetra㉿kali)-[~]
	└─$
1.  Desktop
2.  Documents
3.  Pictures
4.  folder1

Now, of course, directories can contain even more directories within themselves. It becomes a headache when we're having to look through every single one just to try and look for specific files. We can use `find` to do just this for us!

Let's start simple and assume that we already know the name of the file we're looking for — but can't remember where it is exactly! In this case, we're looking for "passwords.txt"

If we remember the filename, we can simply use `find -name passwords.txt` where the command will look through every folder in our current directory for that specific file, like so:

	┌──(tetra㉿kali)-[~]
	└─$ find -name passwords.txt
	./folder1/passwords.txt
	
**"Find"** has managed to _find_ the file — it turns out it is located in folder1/passwords.txt — sweet. But let's say that we don't know the name of the file, or want to search for every file that has an extension such as ".txt". Find let's us do that too!

We can simply use what's known as a wildcard (*) to search for anything that has .txt at the end. In our case, we want to find every .txt file that's in our current directory. We will construct a command such as `find -name *.txt`. Where "Find" has been able to _find_ every .txt file and has then given us the location of each one:

	┌──(tetra㉿kali)-[~]
	└─$ find -name *.txt
	./folder1/passwords.txt 
	./Documents/todo.txt

Find has managed to  _find_:

1.  "passwords.txt" located within "folder1"
2.  "todo.txt" located within "Documents"

### **Using Grep**

Another great utility that is a great one to learn about is the use of `grep`. The `grep` command allows us to search the contents of files for specific values that we are looking for.

Take for example the access log of a web server. In this case, the access.log of a web server has 244 entries.

	┌──(tetra㉿kali)-[~]
	└─$ wc -l access.log
	244 access.log

We can use `grep`to search the entire contents of this file for any entries of the value that we are searching for. Going with the example of a web server's access log, we want to see everything that the IP address "81.143.211.90" has visited (note that this is fictional)

	┌──(tetra㉿kali)-[~]
	└─$ grep  "81.143.211.90" access.log
	81.143.211.90 - - [25/Mar/2021:11:17 + 0000] "GET / HTTP/1.1" 200 417 "-" "Mozilla/5.0 (Linux; Android 7.0; Moto G(4))"

"Grep" has searched through this file and has shown us any entries of what we've provided and that is contained within this log file for the IP.