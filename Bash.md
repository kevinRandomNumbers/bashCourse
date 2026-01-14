# Bash

## Basic commands

### MV
`mv file.txt file_new.txt` => this renames the file
> Be careful with this command, if you rename a file with the same value of another file, this file wil be overridden.

---

### GREP
- `grep test file.txt` => looks for the word 'test' in the file 'file.txt'
- `grep -A1 test file.txt` => looks for the word 'test' and the entire line after it in the file 'file.txt'
- `grep -B1 test file.txt` => looks for the word 'test' and the entire line before it in the file 'file.txt'
- `grep -C1 test file.txt` => looks for the word 'test' and the line before and after it in the file 'file.txt'
- `grep -i test file.txt` => looks for the word 'test' and 'TEST' in the file 'file.txt'
- `grep -o '^t.' file.txt` => returns the word that starts with 't' and one letter after that in the file 'file.txt'
- `grep -o 't$' file.txt` => returns the word that ends with 't' in the file 'file.
---

### LESS
`less` is a pager, if you run this, you see the top of the file and you can paginate through data with the arrow keys. You end it with `q`.

**You can swap `:` to `/` and you can search. If you want to go through the search results you can use `n` and `shift-n` to go back and forward.**

`more` is the same.

---

### RM
`rm -i file*` => will ask you which files to remove instead of deleting it all.

---

### FILE
`file /bin/rm` will show what type of file something is.

---

### TR
The translate function can help you to replace characters inside a string. If you for example do `echo $PATH`, the result will be your path variable seperated by `:`. If you need the seperator to be a newline, you can do `echo $PATH | tr : '/n/'`.

---

### UNAME
`uname -a` prints information about your system.

---
---

## Build-in VS external commands
If you use the command `type history`, you'll notice that history is a build in command rather than an external. External commands live for example in `usr/bin/ls`. You can see this when you type `type -a ls`, you have to use the flag `-a` to list all the locations for `ls`. You need to know this because build-in commands don't have man-pages, you'll need to type `help history` if you need the man-page like help for it. Same goes for the command `which history`, this will return nothing while `which ls` will return the location.



## Basic Variables
- `$PWD` => working directory
- `$USER` => user
- `$SHELL` => shell
- `$HOSTNAME` => hostname
- `$MACHTYPE` => system architecture

### Own variables
If you need to create your own variable for the current session, you can use `name=kevin`. When you then use the command `echo $name`, `kevin` will be printed. You can delete the variable with the command `unset name`.

If you for some reason want the result of a command in a variable, you can use `newVariable = $(uname -a)`


## VIM
`Normal Mode` is the default mode. In here you can make high level adjustments like deleting a line (`dd`), restoring a line (`u`).
When you press `i` you enter insert mode, in this mode you can edit the file like you'd normally do.

To quit VIM, you press `esc` and enter either `q` to quit, or `wq` to write-quit.


## File Permissions
When we use the command `ls -l` we can see that the first section of the result are the permissions for the different directories or files.

With `chmod +x script.sh`, we make a file executable, so we can run a file with `./script.sh` instead of `bash script.sh`


## Scripting

### Checking
To check if a file hasn't got any syntax error, you can run `bash -n script.sh`. If you follow this up with `echo $?` you'll either get a `0` or some other numerical value. If it was `0`, the program ran successfully and no errors where encountered.

---


