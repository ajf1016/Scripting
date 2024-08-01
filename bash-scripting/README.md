# Bash

## Table of Contents

-   [Introduction](#Introduction)
-   [Variables](#Variables)
-   [Input](#Input)
-   [Basic Bash commands](#basic-bash-commands)
-   [Conditional statements (if/else)](#conditional)
-   [Looping and Branching](#looping)
-   [Case statements](#case)
-   [Cron](#cron)
-   [Debuging and Troubleshooting](#debug)

## Introduction

Determine your shell type using the ps command:

```bash
ps
# PID TTY           TIME CMD
# 92140 ttys000    0:00.04 -zsh
# 92200 ttys003    0:00.02 /bin/zsh -il

```

date: Displays the current date

```bash
date  #Tue Mar 14 13:08:57 PKT 2023
```

pwd: Displays the current working directory

```bash
pwd #/home/john/shell-tutorial
```

ls: Lists the contents of the current directory.

```bash
ls # env  log  temp
```

## Variables

There are no data types in Bash. In Bash, a variable is capable of storing numeric values, individual characters, or strings of characters.

```bash
MY_NAME=Nicolas
SAME_NAME=$MY_NAME
```

Valid variable names:

```bash
name
count
_var
myVar
MY_VAR
```

Invalid variable names:

```bash
2ndvar
my var
my-var
```

## Input and Output

We can read the user input using the read command.

```bash
#!/bin/bash

echo "What's your name?"

read entered_name

echo -e "\nWelcome to bash tutorial" $entered_name
```

## Basic Bash commands

```bash
    cd: #Change the directory to a different location.
    ls: #List the contents of the current directory.
    mkdir: #Create a new directory.
    touch: #Create a new file.
    rm: #Remove a file or directory.
    cp: #Copy a file or directory.
    mv: #Move or rename a file or directory.
    echo: #Print text to the terminal.
    cat: #Concatenate and print the contents of a file.
    grep: #Search for a pattern in a file.
    chmod: #Change the permissions of a file or directory.
    sudo: #Run a command with administrative privileges.
    df: #Display the amount of disk space available.
    history: #Show a list of previously executed commands.
    ps: #Display information about running processes.
```
