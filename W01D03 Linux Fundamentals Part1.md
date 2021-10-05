# Linux Fundamentals

## High Level Goals

In this lesson, we're going to learn some more commands for interacting with the filesystem to allow us to:

-  Advancing your knowledge of the filesystem
-  introducing you to the access mechanisms
-  Common Directories

## Advancing your knowledge of the filesystem

In this section, we're going to learn some more commands for interacting with the filesystem to allow us to:

-   create files and folders
-   move files and folders
-   delete files and folders

More specifically, the following commands:

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

Creating files and folders on  Linux  is a simple process. First, we'll cover creating a file. The touch command takes exactly one argument -- the name we want to give the file we create. For example, we can create the file "note" by using `touch note`. 

	=> Using touch to create a new file
	┌──(tetra㉿kali)-[~]
	└─$ touch note
	
	┌──(tetra㉿kali)-[~]
	└─$ ls
	folder1 note

This is a similar process for making a folder, which just involves using the `mkdir` command and again providing the name that we want to assign to the directory. For example, creating the directory "mydirectory" using `mkdir mydirectory`.

	=> Creating a new directory with mkdir
	┌──(tetra㉿kali)-[~]
	└─$ mkdir mydirectory
	
	┌──(tetra㉿kali)-[~]
	└─$ ls
	folder1 mydirectory note

### Removing Files and Folders (rm)

`rm` is extraordinary out of the commands that we've covered so far. You can simply remove files by using `rm`. However, you need to provide the `-R` switch alongside the name of the directory you wish to remove.
```
=> Using rm to remove a file
┌──(tetra㉿kali)-[~]
└─$ rm note
	
┌──(tetra㉿kali)-[~]
└─$ ls
folder1 mydirectory	
```
```
=> Using rm recursively to remove a directory
┌──(tetra㉿kali)-[~]
└─$ rm -R mydirectory

┌──(tetra㉿kali)-[~]
└─$ ls
folder1
```