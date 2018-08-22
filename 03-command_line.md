# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

> > 1. show current working directory path **pwd**
2. creating a directory **mkdir name**
3. deleting a directory **rmdir name**
4. creating a file using 'touth' command **touch filename**
5. deleting a file **rm filename**
6. renaming a file **mv oldfilename newfilename**
7. listing hidden files **ls -a**
8. copying a file from one directory to another **cp filename destination**
9. moving a file or directory **mv filename destination**
10. view the contents of a file **cat filename** 

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

> > ls lists contents (files and directories) of the directory you are currently in
ls -a lists contents of current directory including hidden files
ls -l lists contents in long format
ls -lh lists contents in long format but abbreviates file sizes using unit suffixes (byte, kilobyte, megabyte, etc)
ls -lah lists contents including hidden files in long format with file sizes abbreviated
ls -t lists in order of time modified
ls -Glp lists content in long format with '/' after directories and enabling colorized output

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> > ls -u sort by last access time
ls -m displays contents in a single line separated by commas
ls -R lists subdirectories of all directories
ls -1 displays output as a single column
ls -r sort output in reverse order

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > xargs enables you to pass standard input to use in another command. It reads items (separated by commas) from this input and executes the command for each item. It is useful for performing the same action on multiple files/ directories at once (moving, creating, copying, etc.)

Here is an example:

seq 5 | xargs mkdir
This creates directories labelled 1, 2, 3, 4, 5. The advantage of using xargs is that   you do not have to type mkdir 5 times

 

