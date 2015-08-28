# Bash Cheat Sheet
a quick reference guide to basic operations on the command line.  The only way to "get" these is to use them.

## Navigation
`pwd` present(print?) working directory, outputs your current location.
`ls` list, lists files and directories in the current location.  (useful arguments include `-l` for list view, `-a` for attributes and including hidden files and directories and `-t` for ordering them by time).
`mkdir` for make directory
`cd` for change directory
`cd ..` for change to one directory up the file tree. (NB a single `.` refers to the current location in the filetree)
`mv` for move, can also be used to rename things.
`rmdir dirname` for remove direcotry, (only works if dir is empty)
`touch filename.ext` will create a file
`rm filename.ext` will remove the specified file
`rm -R dirname` will recursively remove all the files and directories in the directory specified.
`clear` clears the current screen 
`history` will list recent commands

**Give these a go.**
Fire up a terminal window and give this a whirl.

````bash
      pwd
      mkdir test_the_terminal
      cd test_the_terminal
      touch test.txt
      touch .hidden.txt
      touch another.txt
      mv another.txt another_one.txt
      touch .secret.txt
      ls
      ls -l
      ls -la
      ls -alt
      cd ..
      rm -R test_the_terminal
      ls
      clear
````



## Editing with Vim
to open a file with vim : 
````bash
    vim somefile.txt
````

Vim has three main modes that you can operate in : 
* normal (press `esc` from where ever you are, and if you're not in normal mode you'll return to normal mode) - which allows you to navigate quickly and run commands, such as save and quit as well as some editing such as deleting a charater..
* insert (press `i`) - which allows 
* visual (press `v`)
