# Bash

## Table of Contents

-   [Introduction](#Introduction)
-   [Variables](#Variables)
-   [Input](#Input)
-   [Output](#Output)
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
