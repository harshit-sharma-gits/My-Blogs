---
title: "Essential Linux Commands everyone should know"
seoTitle: "15 Essential Linux Commands"
seoDescription: "Essential linux commands
Linux commands
Bash Scripting
How to write Linux commands
Linux commands in terminal
Ubuntu commands
common commands
How to write"
datePublished: Thu Jan 26 2023 18:22:45 GMT+0000 (Coordinated Universal Time)
cuid: clddfaltf000709l36mdsd5hd
slug: essential-linux-commands-everyone-should-know
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1674733786441/115a2844-321d-40a5-ae33-b8def0c54ff9.jpeg
tags: ubuntu, linux, bash, command-line, cli

---

A Linux command is a program and/or utility that runs on the CLI (Command Line Interface). Linux commands are executed on the terminal. These commands have usage ranging from package management to file manipulation.

A basic Linux command syntax looks like this

```apache
command [option(s)] [parameter(s)]
```

One thing you should keep in your mind, Linux Commands are case-sensitive.

For trying out the commands, you might want to pull up a terminal.

### 15 Commonly used Linux Commands

* **ls command**
    

The `ls` command is used to display a directory's files and folders.

This command is very useful if you want to explore the contents of the directory without navigating to the GUI Folder.

```apache
ls -l
```

* **cd command**
    

'cd' expands to **c**hange **d**irectory which gives us a fair hint of what this command does. It is used to change the current working directory to a specified folder inside the terminal.

```apache
cd src/
```

This would move you to the 'src' directory.

If you want to move up to the parent directory, then use `..` like this:

```apache
cd ..
```

* **pwd command**
    

'pwd' translates to **P**rint **W**orking **D**irectory and it is used to display the path of current working directory.

```apache
pwd
```

* **echo command**
    

The `echo` command displays a string which is passed in as an arguement. For example:

```apache
echo "random string"
```

This will display `random string` as an output.

`echo -e "Amesome \nBlog"` : The `-e` flag enables the echo command to recognize the backslash escape sequences inside the arguement.

```apache
$ echo -e "Amesome \nBlog"
Awesome
Blog
```

* **mkdir command**
    

The 'mkdir' command is used to create new directories inside the current working directory from the terminal.

```apache
mkdir <foldername>
```

* **rm command**
    

The 'rm' command helps to delete files and directories. For example:

```apache
rm index.html
```

This line would remove the file 'index.html' from the current working directory.

If you want to remove a directory, then supply the `rm` command with `-R` flag, like this:

```apache
rm -R folderName
```

* **rmdir command**
    

The 'rmdir' command provides the utility to remove empty directories from the system. If the directory contains any files/folders inside it, 'rmdir' will throw up an error. Syntax:

```apache
rmdir folderName
```

* **man command**
    

The 'man' command is used to display the documentation/mannual of any Linuz command that can be run on the terminal.

If we want to see the documentation/mannual of `ls` command, we would write:

```apache
man ls
```

* **cat command**
    

The 'cat' command is used to read the contents of one or more files and display their contents inside the terminal. For example:

```apache
cat file.txt
```

This would print the contents of 'file.txt' onto the terminal. If we write:

```apache
cat -n file.txt
```

This would print the contents of 'file.txt' along with the line numbers.

Suppose we want to concatenate the contents of 'file.txt' and 'names.txt' and place them in another file 'another.txt', we would write:

```apache
cat file.txt names.txt > another.txt
```

* **touch command**
    

The 'touch' command is ussed to create a new file without any content inside it. For example:

```apache
touch style.css
```

This would make a file named 'style.css' in the working directory. Multiple files can be created simlutaneously as:

```apache
touch index.html style.js
```

* **mv command**
    

The 'mv' command expands to **move** and it performs two major functions:

1. It helps to rename a file/directory.
    
2. It helps to move a file/directory from one location to another.
    

Syntax:

```apache
mv <source> <destination>
```

Example:

```apache
mv style.css src/
```

This would move the file 'style.css' to 'src/' directory.

Syntax for renaming:

```apache
mv <initial_filename> <new_filename>
```

Example:

```apache
mv style.css newStyle.css
```

The file name changed from 'style.css' to 'newStyle.css'.

* **cp command**
    

The 'cp' command expands to **copy** and it helps to copy files/directory from one location to another. For example:

```apache
cp style.css src/style.css
```

This would copy the file 'style.css' to the 'src/' folder.

* **tree command**
    

The 'tree' command can be used to list out the contents of directories in a tree-like fashion.

```apache
tree
```

* **head command**
    

The 'head' command prints the first N lines of a given file content. For example:

```apache
head -n 5 style.css
```

This would print the first 5 lines of the file 'style.css'.

* **tail command**
    

The 'tail' command prints the last N lines of a given file content. For example:

```apache
tail -n 3 style.css
```

This would print the last 3 lines of the file 'style.css'.

There you go with the 15 Linux commands. Pretty awesome right! ✨

Connect with me:

🔗 **LinkedIn:** [**https://www.linkedin.com/in/harshit-sharma--/**](https://www.linkedin.com/in/harshit-sharma--/)

🔗 **My YouTube Channel:** [**https://www.youtube.com/c/CoderBuddy?sub\_confirmation=1**](https://www.youtube.com/c/CoderBuddy?sub_confirmation=1)

🔗 **GitHub:** [**https://github.com/harshit-sharma-gits**](https://github.com/harshit-sharma-gits)