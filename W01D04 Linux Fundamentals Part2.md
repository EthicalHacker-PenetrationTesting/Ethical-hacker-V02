# Linux Fundamentals

## High Level Goals

By the end of this lesson, you will be familiar with the following:

-  Advancing your knowledge of the filesystem
-  Switching Between Users
-  Common Directories

## Advancing your knowledge of the filesystem

| Command | Full Name | Purpose |
|--|--|--|
| touch | touch | Create file |
| mkdir | make directory | Create a folder |
| cp | copy | Copy a file or folder |
| mv | move | Move a file or folder |
| rm | remove | Remove a file or folder |
| file | file | Determine the type of file |

> _Protip: Similarly to using cat, we can provide full file paths, i.e. directory1/directory2/note for all of these commands_

### Creating Files and Folders (touch, mkdir)

Creating files and folders on  Linux  is a simple process. First, we'll cover creating a file. The touch command takes exactly one argument -- the name we want to give the file we create.

	→ Using touch to create a new file
	┌──(tetra㉿kali)-[~]
	└─$ touch note
	
	┌──(tetra㉿kali)-[~]
	└─$ ls
	Download note

This is a similar process for making a folder, which just involves using the `mkdir` command and again providing the name that we want to assign to the directory. 

	→ Creating a new directory with mkdir
	┌──(tetra㉿kali)-[~]
	└─$ mkdir mydirectory
	
	┌──(tetra㉿kali)-[~]
	└─$ ls
	Download mydirectory note

### Removing Files and Folders (rm)

`rm` is extraordinary out of the commands that we've covered so far. You can simply remove files by using `rm`. However, you need to provide the `-R` switch alongside the name of the directory you wish to remove.
```
→ Using rm to remove a file
┌──(tetra㉿kali)-[~]
└─$ rm note
	
┌──(tetra㉿kali)-[~]
└─$ ls
Download mydirectory	
```
```
→ Using rm recursively to remove a directory
┌──(tetra㉿kali)-[~]
└─$ rm -R mydirectory

┌──(tetra㉿kali)-[~]
└─$ ls
Download
```

### Copying and Moving Files and Folders (cp, mv)

Copying and moving files is an important functionality on a  Linux  machine. Starting with `cp`, this command takes two arguments:

1. the name of the existing file
2. the name we wish to assign to the new file when copying

`cp`  copies the entire contents of the existing file into the new file. In the command below, we are copying "note" to "note2".

```
→ Using cp to copy a file
┌──(tetra㉿kali)-[~]
└─$ cp note note2
Download note note2
```
Moving a file takes two arguments, `mv` will merge or modify the second file that we provide as an argument. Not only can you use `mv` to move a file to a new folder, but you can also use `mv` to rename a file or folder. 
```
→ Using mv to move a file
┌──(tetra㉿kali)-[~]
└─$ mv note2 note3

┌──(tetra㉿kali)-[~]
└─$ ls 
Download note note3
```

### Determining File Type
**file** command it's showing us the type of the file. 

> This command takes one argument. 
```
→ Using file to determine the contents of a file or the folder.
┌──(tetra㉿kali)-[~]
└─$ file note
note: ASCII text
```

## Switching Between Users

To switching between users in Linux, we will use `su` command, **su** mean **S**witch **U**sers. You are required to know two things to facilitate this transition of user accounts:

-   The user we wish to switch to
-   The user's password


		→ Using su to switch users
		┌──(tetra㉿kali)-[~]
		└─$ su user2
		Password:
		┌──(user2㉿kali)-[~]
		└─$ 
		
## Common Directories
| Directories Name | Full name | what is it |
|--|--|--|
| **/etc** | **etcetera** | The etc folder is a commonplace location to store system files that are used by your operating system. |
| **/var** | **variable data** | This folder stores data that is frequently accessed or written by services or applications running on the system. |
| /**root** | **"root" system user** | The root is the username or account that by default has access to all commands and files on a Linux |
| **/tmp** | **temporary** | The /tmp directory is volatile and is used to store data that is only needed to be accessed once or twice. |

## Practice 

1. What is the directory path that would we expect logs to be stored in?

2. What would the command be to switch to the user "user2"?

3.  How would you create the file named "newnote"?

4. How would we move the file "myfile" to the directory "myfolder"
		
