# Lab Report

## `cd`
![image](https://github.com/AskewParity/cse15l-lab-reports/assets/87111319/4749c700-8eae-4447-b71e-f28c686904d1)

The command `cd` with no further commands changes the working directory to the home directory `~]`. This is not an error.

The previous working directory was: `/home/lecture1`

The working directory after the command was: `/home`

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/87111319/b55e5033-6209-4907-a8b9-e4f9be09e532)

The command `cd` with another folder (that the current directory has access too) as an argument changes the working directory to that folder (i.e. `[WORKING_DIRECTORY]/folder/`. This is not an error.

The previous working directory was: `/home/lecture1`

The working directory after the command was: `/home/lecture1/messages`

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/87111319/51d82f47-23ac-4182-a59d-2e486903d3ed)

The command `cd` with a file as an argument doesn't change the working directory. This is an error, as `cd` can not enter the file as a new working directory.

The previous working directory was: `/home/lecture1`

The working directory after the command was: `/home/lecture1`

## `ls`

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/87111319/dff3a56e-af4a-4445-b3a4-b604ccc61262)

The command `ls` with no argument prints out all the folders and files (direct children) in the current working directory. It does not change the working directory. This is not an error.

The previous working directory was: `/home/lecture1`

The working directory after the command was: `/home/lecture1`

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/87111319/9a189de1-99b1-4d7d-a62c-bfbf6656b669)

The command `ls` with a folder/directory as an argument prints out all the folders and files in (direct children) of that directory. This is not an error

The previous working directory was: `/home/lecture1`

The working directory after the command was: `/home/lecture1`

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/87111319/0fb57c69-a041-4f5b-b2aa-ec644cd27b7b)

The command `ls` with a file as an argument just prints out the name of that file. This is not an error. 

The previous working directory was: `/home/lecture1`

The working directory after the command was: `/home/lecture1`

## `cat`

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/87111319/052c75fb-5453-468d-bdc9-82c8ddfdd5b5)

The command `cat` with no arguments keeps a running process open, but otherwise doesn't do anything. When text is typed into the console, the program prints the text back verbatim. This is not an error (it is just reading from standard input).

The previous working directory was: `/home/lecture1`

The working directory after the command was: `/home/lecture1`

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/87111319/b7f9c915-c535-4efd-aeb6-1a4a942c5b3a)

The command `cat` with a folder/directory as an argument throws an error message. This is an error, and the program can not print out the contents of a directory.

The previous working directory was: `/home/lecture1`

The working directory after the command was: `/home/lecture1`

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/87111319/e906508f-048f-4b25-b3c6-17e905ecefbc)

The command `cat` with a file as an argument prints out the content to the console. This is not an error.

The previous working directory was: `/home/lecture1`

The working directory after the command was: `/home/lecture1`

