# Bash

## Table of Contents

-   [Introduction](#Introduction)
-   [Variables](#Variables)
-   [Input](#Input)
-   [Basic Bash commands](#Basic-Bash-Commands)
-   [Conditional statements (if/else)](#Conditional)
-   [Looping and Branching](#Looping)
-   [Case statements](#Case-statements)
-   [Functions](#Functions)
-   [Array](#Array)
-   [Cron](#Cron)
-   [Debuging and Troubleshooting](#Debug)
-   [Modular Scripting](#Modular-Scripting)

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

## Input

We can read the user input using the read command.

```bash
#!/bin/bash

echo "What's your name?"

read entered_name

echo -e "\nWelcome to bash tutorial" $entered_name
```

## Basic-Bash-Commands

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

## Conditional

There are several ways to evaluate conditions, including if, if-else, if-elif-else, and nested conditionals.

```bash
if [[ condition ]];
then
	statement
elif [[ condition ]]; then
	statement
else
	do this by default
fi
```

We can use logical operators such as AND -a and OR -o to make comparisons that have more significance.

```bash
if [ $a -gt 60 -a $b -lt 100 ]
```

```bash
#!/bin/bash

echo "Please enter a number: "
read num

if [ $num -gt 0 ]; then
  echo "$num is positive"
elif [ $num -lt 0 ]; then
  echo "$num is negative"
else
  echo "$num is zero"
fi
```

## Looping

while loop

```bash
#!/bin/bash
i=1
while [[ $i -le 10 ]] ; do
   echo "$i"
  (( i += 1 ))
done
```

for loop

```bash
#!/bin/bash

for i in {1..5}
do
    echo $i
done
```

## Case-statements

```bash
case expression in
    pattern1)
        # code to execute if expression matches pattern1
        ;;
    pattern2)
        # code to execute if expression matches pattern2
        ;;
    pattern3)
        # code to execute if expression matches pattern3
        ;;
    *)
        # code to execute if none of the above patterns match expression
        ;;
esac
```

```bash
fruit="apple"

case $fruit in
    "apple")
        echo "This is a red fruit."
        ;;
    "banana")
        echo "This is a yellow fruit."
        ;;
    "orange")
        echo "This is an orange fruit."
        ;;
    *)
        echo "Unknown fruit."
        ;;
esac
```

## Arrays

Creating Arrays in Shell Scripts

```bash
indexed_array[0]="Fruit"
```

Accessing Array Elements Individually

```bash
   echo ${indexed_array[0]}

   index_array=(1 2 3 4 5 6)
   echo ${index_array[0]}
```

## Functions

First method

```bash
my_function(){
    echo "Hello world"
}
```

Second method useing reserved keyword(Function)

```bash
function my_function(){
    echo "Hello world"
}
```

## Crone

Schedule Scripts using cron
Below is the syntax to schedule crons:

```bash

# Cron job example
* * * * * bash /path/to/script.sh
```

Here, the \*s represent minute(s) hour(s) day(s) month(s) weekday(s), respectively.

```bash
#Schedule       Description                                             #cron job example
0 0 * * * 	    Run a script at midnight every day 	                    0 0 * * * /path/to/script.sh
*/5 * * * * 	Run a script every 5 minutes 	                        */5 * * * * /path/to/script.sh
0 6 * * 1-5 	Run a script at 6 am from Monday to Friday 	            0 6 * * 1-5 /path/to/script.sh
0 0 1-7 * * 	Run a script on the first 7 days of every month 	    0 0 1-7 * * /path/to/script.sh
0 12 1 * * 	    Run a script on the first day of every month at noon 	0 12 1 * * /path/to/script.sh
```

## Debug

Set the set -x option

```bash
#!/bin/bash

set -x

# Your script goes here
```

Check the exit code

```bash
#!/bin/bash

# Your script goes here

if [ $? -ne 0 ]; then
    echo "Error occurred."
fi
```

Use the set -e option

```bash
#!/bin/bash

set -e

# Your script goes here
```

## Modular Scripting

Modular scripting refers to the practice of breaking down scripts into smaller, reusable, and manageable components or modules.

-Main Script (main_script.sh)

```bash
#!/bin/bash

# Source the utility functions
source ./utilities.sh
source ./network.sh

# Main script logic
echo "Starting the main script..."

# Use functions from the sourced files
create_user "john"
check_network

echo "Main script completed."

```

-Utility Functions (utilities.sh)

```bash
#!/bin/bash

# Function to create a user
create_user() {
  local username=$1
  sudo useradd -m "$username"
  echo "User $username created."
}
```

-Network Functions (network.sh)

```bash
    #!/bin/bash

# Function to check network connectivity
check_network() {
  ping -c 1 google.com &> /dev/null
  if [ $? -eq 0 ]; then
    echo "Network is up."
  else
    echo "Network is down."
  fi
}

```
