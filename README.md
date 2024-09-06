The Bash Command Line
=====================

![*Tux, the Linux penguin*](tux.png)

This tutorial makes you familiar with **bash**, the Linux command line. You will learn to:

* navigate directories
* manipulate files
* execute programs

If you have no previous experience with Unix-like
systems or know a few commands but would like to know more, this tutorial is for you.

### Prerequisites

*This tutorial was prepared for Ubuntu Linux, but it works on MacOS,
Cygwin and the Git bash as well, given that Python 3 is installed on
your system.*

----

## Goal

In this tutorial, you will be looking for a sentence containing 17 characters.


Solution:
```
___________ ______
```

All characters are hidden in the exercises below.

## Preparations

* clone the repository using git
* locate the  `exercises/` folder
* open a `bash` terminal

![](preparations.png)

----

## 1. Directories and files


### 1.1. Navigating directories

The **first character** is hidden in a file somewhere in the *exercise1*
directory tree. Use the commands

``` {.sourceCode .bash}
cd <directory_name>
```

(do not type the pointy brackets, just insert the directory name) and

``` {.sourceCode .bash}
ls
```

to move from one directory to the next. Look through subdirectories
until you find one with the name `solution_1.1` and list its contents.
If you went to a wrong directory, you can go back one level by typing:

``` {.sourceCode .bash}
cd ..
```

or go back to your home folder:

``` {.sourceCode .bash}
cd
```
you can also use the \~ character to refer to you home directory:

``` {.sourceCode .bash}
cd ~
```

Additionaly, you can print the absolute path of your current directory using

``` {.sourceCode .bash}
pwd
```

### 1.2. Show a hidden file

Some files are not visible immediately. To see them, you need the
command

``` {.sourceCode .bash}
ls -a
```

The **second character**, is in the same directory as the first one, but
in a hidden file.

### 1.3. Execute a bash script 

Use cd .. to go back to the directory `exercise_1/directoryB/`. 
To find the **third character**, you need to execute the
bash script. On bash, this is done by typing 'source' and the name of the
program:

``` {.sourceCode .bash}
source program.sh
```

You can run a bash script by using the ./ operator

``` {.sourceCode .bash}
./program.sh
```

What? It does not work? You can use the ./ operator only on executable files!
Add executable permisions to program.sh, then run it using ./

``` {.sourceCode .bash}
chmod +x program.sh
```

+x means "add executable permissions".

Did you know? You can run multiple commands sequentially using the ; operator

``` {.sourceCode .bash}
chmod +x program.sh ; ./program.sh
```


### 1.4. Find out how big a file is

Go to the folder `exercise_1/directoryC/`. To find **the fourth
character**, you need to find out how big the text file in the directory
is. This is done with the command

``` {.sourceCode .bash}
ls -l
```

In the table the command produces, you will find the file size in bytes,
the file’s owner, permissions to read and modify it, and the date/time
of the last modification.

To obtain the fourth character look up the file size in the [Table of
printable ASCII
characters](https://en.wikipedia.org/wiki/ASCII#Printable_characters):

![](ASCII-Table-wide.svg)

*ASCII Table, Public Domain*

<div class="admonition hint">

When typing names of directories or files, press `[TAB]` after the first
few characters. Unix tries to guess what you are typing.

</div>

### 1.5. Creating files

Did you know? You can use the 'touch' command to update the modification time of files.
If the file you are touching does not exists, 'touch' will create it. The following commands creates
the file new\_file.txt
Run the following command to observe the effect of touch:

``` {.sourceCode .bash}
touch new_file.txt
```

----

## 2. Edit text files

Please use `cd ..` to go back to the top directory of the tutorial
material. Then, change to the directory `exercise_2`.

### 2.1. See the content of a text file

In the directory *exercise\_2/*, you will find a text file
*solution\_2.1.txt*. The **fifth character** is inside that file. To see
its contents, use the command

``` {.sourceCode .bash}
cat <filename>
```

You can also use the command 'less' to view the content of a file in a minimal text browser

``` {.sourceCode .bash}
less <filename>
```

Press 'q' to exit.

### 2.2. Edit text files and manual

You can edit files by opening a text editor such as VSCode or Vim.
Fill text file with the characters you have found so far.


<div class="admonition hint">

If you want to know more about a particular command, type

``` {.sourceCode .bash}
man <command>
```

You get shown a help page that you can leave by pressing 'q'.

</div>

----

## 3. Copy and remove files

Please go to the directory exercise\_3.

### 3.1. Create a directory and copy a file to it.

To find **characters six, seven and eight**, you need to create a
subdirectory named *solution* in `exercise_3/` and copy the files from
the `part1/` and `part2/` folders into it.

For creating directories, use the command:

``` {.sourceCode .bash}
mkdir <directory name>
```

For copying, you can use the command

``` {.sourceCode .bash}
cp <filename from> <filename to>
```

Type `ls -l solution/*` afterwards to see the solution.



Did you know? Instead of copying, you can use the 'mv' command to move files and directories.
The 'mv' command is especially useful to change the name of files or directories


``` {.sourceCode .bash}
mv <path to filename> <new path to new filename>
```

Use the command to move the directory 'solution' to you home, change the name of the directory to 'toBeRemoved'


### 3.2. Removing files

In the `data` directory, all files with an `Y` need to be deleted. To do
so, use the command:

``` {.sourceCode .bash}
rm <filename>
```

Also, there are more files to be deleted in the *data* directory. To
remove more than one file at once, you can use `*` as a wildcard, i.e.
`rm ju*` will delete all of `junk.txt, juniper.txt` and `june.docx`.

To get **characters nine and ten**, look at the files that remain after
deleting all that contain a `Y`.

<div class="admonition hint">

To remove an empty directory, you can use

``` {.sourceCode .bash}
rmdir <directory name>
```

The command

``` {.sourceCode .bash}
rm -r <directory name>
```

deletes a directory and everything in it.

Use the rm -r command to remove the 'toBeRemoved' directory in your home.

</div>

<div class="admonition warning">

On Unix, it is not possible to undelete files!

This makes removing files with the `*` symbol **very** dangerous,
because you could wipe out everything with a single command (e.g. if you
type the wrong directory by accident). Backups become an even better
idea after learning this command.

</div>

----

## 4. Process text data

Please go to the directory exercise\_4.

### 4.1. comparing two files

There are two different versions of a quote, `ai.txt`, and
`artificial_intelligence.txt`. To find out, how they differ, Unix
provides the command

``` {.sourceCode .bash}
diff <filename1> <filename2>
```

The **11th character** of the solution is the single character in which the
two files differ.

### 4.2. Sorting a text file

Unix has a small program to sort text files alphabetically. It is called
by

``` {.sourceCode .bash}
cat <filename> | sort
```

The symbol '|' is called a pipe and is often used to connect Unix programs to each other.
In this case, the output of 'cat' is used as input for 'sort'. The **12th character** of the solution is the
first character of the last word in the alphabetically sorted file
elephant.txt.

### 4.3. Redirecting output

You can use the '>' and '>>' to redirect the output of a command.
For example, you can use '>' to redirect the output of 'echo' to file.
'echo' is a simple program that writes a string "\<string\>" to the standard output.


``` {.sourceCode .bash}
echo "new content" > outOfEcho.txt
```
Use 'cat' to see the content of outOfEcho.txt

Warning: If outOfEcho.txt does not exist, it will be created; furthermore, if outOfEcho.txt exists, its content will be erased!

You can use '>>' to append to the end of a file without erasing its content:

``` {.sourceCode .bash}
echo "new appended content" >> outOfEcho.txt
```
</div>

After running the previous two commands. The **13th character** of the solution is the letter of the alphabet corresponding to the
number of words in outOfEcho.txt




### 4.4. Finding words in a text file

To look for specific words in a text file, use the command

``` {.sourceCode .bash}
grep <word> <filename>
```

It produces all lines from the given file that contain the given word.
The `grep` command is very powerful and can handle Regular Expressions.

To find the **14th character**, search for the word **fire** in the file
`datascience.txt` and take the **first** character of the output.

<div class="admonition hint">

You can search through many files at once by including a \* in the
filename.

</div>

----

## 5. Command-line tools

The following can be done in any directory.

### 5.1. Check whether you have internet

The easiest way to check from the Unix command line whether the internet
connection works, is to send a request to a known server (e.g.
www.spiced-academy.com) using the command

``` {.sourceCode .bash}
ping <web address>
```

The command reports, how long a message takes back and forth to the
given server. To interrupt the messages, press Ctrl+C.

The **15th character** is the `ping` option that sets the maximum number
of requests to send before terminating the program. Check the documentation with:

``` {.sourceCode .bash}
man ping
```

### 5.2. Set an environment variable

To install some programs, it is necessary to set so-called environment
variables. These can be set using the command

``` {.sourceCode .bash}
export <variable-name>=<value>
```

You can see all variables by the command

``` {.sourceCode .bash}
env
```

To obtain the **16th character**, you need to use `export` to set the
variable *GIVEME* to the value **UNCHARACTERISTICALLY**.

``` {.sourceCode .bash}
echo $GIVEME
```

Find out the **character position in the alphabet** with:

``` {.sourceCode .bash}
echo $GIVEME | wc -c
```

Use the following command to understand the meaning of 'wc -c'

``` {.sourceCode .bash}
man wc
```

<div class="admonition hint">

By default, changes to environment variables only affect the current
terminal.

If you want to set environment variables for each console window, write
the export command to the file `.bashrc` in your home directory (it is a
hidden file).

</div>


### 5.3. Managing processes

To see what programs are running on your machine, type

``` {.sourceCode .bash}
top
```

It displays you a list of all currently active programs. *Shift+P* sorts
them by the CPU time they are using, *Shift+M* by the amount of memory
they are using (if you don't see any program consuming lots of memory,
start a web browser). Quit `top` by pressing *q*.

The **last character** of the solution is the first character of the first word in the line containing the column labels.

<div class="admonition hint">

If you want to get rid of one of the programs you started, you can do so by typing

``` {.sourceCode .bash}
kill -s 9 <pid>
```

</div>

The 'kill' command sends a signal to the process with the specified \<pid\>.
9 specifies that you want to send a termination signal.


You find the pid number in the first column of the *top* output. Of
course, you may only interrupt your own programs, not those owned by
*root*, the system administrator.

You can also show the lists of processes using the 'ps' command:
``` {.sourceCode .bash}
ps a
```
The 'a' option means 'all'.

----

### License

**© 2010 Dr. Kristian Rother**

This tutorial is published under the Creative Commons Attribution
Share-alike License 4.0

Forked from [<https://github.com/krother/bash_tutorial>](https://github.com/krother/bash_tutorial).

Extended by Samuele Germiniani 2024.

### Solution

APTENODYTES TEACUP
