---
title: "Complete guide to BASH Scripting"
seoTitle: "A Complete Guide to BASH Scripting"
seoDescription: "Follow along with this BASH Scripting guide to gain knowledge of Variables, Control Statements, Loops, Maths in BASH."
datePublished: Wed Jul 19 2023 09:34:14 GMT+0000 (Coordinated Universal Time)
cuid: clk9j15ka000009l15zdwf4nl
slug: complete-guide-to-bash-scripting
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689580866170/a956d061-6280-4939-b56d-ca95325f1526.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689759175902/a46bcfdf-8620-4f03-bbb1-f9dea2b96b18.gif
tags: linux, bash, devops, linux-for-beginners, wemakedevs

---

## Overview

As a DevOps professional (or a beginner), you will be writing a ton of commands. And at some point, you will run into a situation where you are writing duplicate commands. So why not automate it? And Bash Scripting comes into play here.

Bash (you may say) is a whole programming language as it has variables, loops, functions, etc.

But technically speaking, Bash is a shell that lets you interact via commands. You can also check out what SHELL you are using in your terminal by entering:

```bash
echo $SHELL
```

Output: `/bin/bash` It means that we are using bash.

## What is a Bash Script?

In general, a script is essentially a file that has one or more commands written inside. And when the script is executed, the commands are run.

### Let's create a simple Bash Script!

1. **Make a file**
    
    ```bash
    touch myscript.sh
    ```
    
2. **Put a command in it**
    
    Let's just put an `ls` command inside it. So when we run `myscript.sh`, `ls` will be executed.
    
    To write in the script file, you can here use `echo` command, as we have only one line to write.
    
    ```bash
    echo "ls" > script.sh 
    ```
    
    But when you will be writing long scripts, text editor like **nano** will be much useful.
    
3. **Mark it executable**
    
    ```bash
    sudo chmod +x myscript.sh
    ```
    
4. **Execute it**
    
    ```bash
    ./myscript.sh
    ```
    
    And you will see the output for `ls` command.
    

Voila! You have written your first Bash Script.

### Mark your script to be BASH Only

You can make the script execute under BASH irrespective of whatsoever shell you are using, by adding this as the first line:

```bash
#!/bin/bash
```

So, you have created your first BASH Script. But hold on, there is so much more to learn in it. Let me walk you through this, one by one.

## Using Variables in BASH

If you have some exposure to programming in general, then you must be familiar with **Variables**. They are just named storage locations. See the following BASH Script:

```bash
#!/bin/bash

myName="Harshit"
myAge="21"

echo "Hello my name is $myName"
echo "I am $myAge years old."
```

The most basic use of variables is shown in this script. Rather than predefining the contents of a variable, you can also read the variable from the user like this:

```bash
#!/bin/bash

echo "Enter you name: "
read name

echo "Hi $name it is nice to meet you"

# IMPORTANT TO NOTE
# Here I have used double-quotes with echo
# Single-quotes won't work with echo when you're doing something with variables
# If I have used single-quotes it would have just printed the variable name
```

`read` can also take some options. Look at these examples below:

```bash
#!/bin/bash

read -p "Enter your username: " username
read -ps "Enter your password: " passwd

# -p Outputs the prompt before taking input
# -s Reads the user input silently
# See we have merged two commands (-p and -s) as -ps
```

### Store the output of a command in a variable

```bash
currentTime = $(date +"%T")
```

The output of `date +"%T"` command is stored in the `currentTime` variable.

## Using maths with BASH

You can use `let` and `expr`.

```bash
let a=5+4
echo $a  #9

let "a = 5 + 4"
echo $a # 9

let a++
echo $a # 10

let "a = 4 * 5"
echo $a # 20
```

```bash
a=$(( 5+4 ))
echo $a #9

(( a++ ))
echo $a #10
```

## IF Statements in BASH

Check out this script:

```bash
#!/bin/bash

myNum=200

if [ $myNum -eq 200 ]
then
    echo "Variable equals 200"
else
    echo "Variable does not equals 200"
fi
```

You can also use the if-elif-else block as follows:

```bash
#!/bin/bash

num=200

if [ $num -eq 200 ]
then
    echo "Number is 200"
elif [ $num -eq 150 ]
then
    echo "Number is 150"
else
    echo "It is something else"
fi
```

You may notice we are not using operators for comparison. Instead of '==' we are using '-eq'. Similarly these are used:

| Operation | Operator |
| --- | --- |
| Equals to | \-eq |
| Greater than | \-gt |
| Less than | \-lt |
| Directory Exists | \-d |
| File Exists | \-f |
| Expression is false | ! |

### Loops!

You can use the **while** loop as follows:

```bash
#!/bin/bash

# while [ <condition> ]
# do
#     <commands>
# done

counter=0
while [ $counter -lt 10 ]
do
    echo $counter
    ((counter++))
done
```

You can use the **for** loop as follows:

```bash
#!/bin/bash

names='Harshit Harsh Ayush Ashish'

for name in $names
do
    echo $name
done

for n in {1..10}
do
    echo $n
done
```

### Functions in BASH

Just like any other programming language, you can use functions in BASH as well. See this simple example of a function:

```bash
#!/bin/bash

say_hello() {            # Function Definition
    echo "Hello World"
}

say_hello                # Calling the function


# PASSING AN ARGUEMENT

say_hello_to() {
    echo "Hello $1"
}

say_hello_to Harshit    # Outputs Hello Harshit


# RETURN VALUES

myFunction() {
    echo "This is my awesome function!"
    return 3
}

myFunction
echo "The above function has return value of #?"
# PS: It used an exit code!
```

These are the most basic commands you are going to use in BASH. Now obviously, BASH Scripting is so much more than this. But this blog was intended to give you a basic idea about BASH. And it did!

## Conclusion

If you have followed this blog, you now have a pretty good idea about BASH Scripting. Though you may not be able to write a production-ready script yet as it requires the use of more commands, you will be able to figure you what is happening in any script.

If you find this blog to be helpful, please give an upvote. ✨