<h3 align="center">LAB ASSIGNMENT 5</h3>

<div align="center">

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![GitHub Issues](https://img.shields.io/github/issues/mayank-pq2q4/LAB4.svg)](https://github.com/mayank-pq2q4/LAB4/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/mayank-pq2q4/LAB4.svg)](https://github.com/mayank-pq2q4/LAB4/pulls)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

</div>

---

<p align="center"> Trying to mimic a shell program.
    <br> 
</p>

## 📝 Table of Contents

- [About](#about)
- [Getting Started](#getting_started)
- [Usage](#usage)
- [Built Using](#built_using)
- [TODO](../TODO.md)
- [Contributing](../CONTRIBUTING.md)
- [Authors](#authors)
- [Acknowledgments](#acknowledgement)

## 🧐 About <a name = "about"></a>

Lab 5:  Expanding on Labs 2-4: Creating an interactive shell with signal handling capability.

In this lab task, unix type shell which will read commands from the user and execute them appropriately. There are two types of commands that can be expected from the user : a user-defined command and a system-command. The following are the specifications for the project. For each of the requirement the appropriate example is given along with it.

Specification -1 : Display requirement

When you execute your code a shell prompt of the following form must appear:

<username@system_name:curr_dir>.

E.g., <manish@research:~>

The directory from which the shell is invoked will be the home directory of the shell and should be indicated by "~"

If the user executes "cd" change dir then the corresponding change must be reflected in the shell as well.

E.g., ./a.out
<manish@research:~>cd newdir
<manish@research:~/newdir>

Specification -2 :  User-defined commands

The following commands must be supported by the shell
-pid : prints the process id of your shell program

E.g., 
<manish@research:~>pid
command name: ./a.out  process id: 234

-pid current : prints the list of the process ids of the processes that are created by the shell and currently active
<manish@research:~>pid current
List of currently executing processes spawned from this shell:
command name: emacs   process id: 235
command name: xbiff   process id: 448
command name: xcalc   process id: 459

-pid all : prints the list of process ids of all commands that were executed so far by the shell (including the currently executing processes)

E.g.,
<manish@research:~>pid current
List of all processes spawned from this shell:
command name: ls      process id : 112
command name: cd      process id : 124
command name: emacs   process id : 235
command name: xbiff   process id : 448
command name: xcalc   process id : 459


-hist : list of all commands, in chronological order, executed by the shell so far

E.g., 
<manish@research:~>hist
1. ls
2. cd
3. emacs
4. xbiff
5. xcalc
6. vi
7. ps

-histn: list of last "n" commands executed by the shell. If the number of commands is less than "n" then the shell should print only the available number of commands. 

E.g.,
<manish@research:~>hist5 (Say print last 5 commands assuming the above history of commands)

1. emacs
2. xbiff
3. xcalc
4. vi
5. ps


-!histn : execute history command number "n" (assuming the first command is numbered 1)

E.g.,
<manish@research:~>!hist4 (assuming above history of commands)
vi

Specification 4: System commands with and without arguments

All other commands are treated as system commands like : ls, emacs, vi and so on. The shell must be able to execute them either in the backgroud or in the foreground.

--Foreground processes: For example, executing a "vi" command in the foreground implies that your shell will wait for this process to complete and regain control when this process exits.

--Background processes: Any command invoked with "&" is treated as background command. This implies that your shell will spawn that process and doesn't wait for the process to exit. It will keep taking user commands. If the background process  exits then the shell must display the appropriate message to the user.

Specification 5:  General notes

1. Use exec family of commands to execute system commands. If the command cannot be run or returns an error it should be handled approiately. Look at perror.h for appropriate routines to handle errors.

2. Use fork() for creating child processes where needed and wait() for handling child processes

3. Use signal handlers to process signals from exiting background processes. Marks will be deducted if proper signal handling is not done.

4. You can use : uname, hostname, whomai commands to get the shell display working.  For respective header libraries use: man <cmd>

5. The user can type the command anywhere in the command line i.e., by giving spaces, tabs etc. Your shell should be able to handle such scenarios appropriately. 

6. Segmentation faults at the time of grading will be penalized.


## 🏁 Getting Started <a name = "getting_started"></a>

Download as zip. Then unzip. Then,
To compile: `make`. To run: `./shl`, to check for memory leaks (runs it with valgrind): `make leaks`


### Prerequisites

Make sure you have valgrind installed for memory debugging or memory leaks detection, or `make leaks` wont work.

```
sudo apt-get install valgrind
```


## 🎈 Usage <a name="usage"></a>

Type `compgen` or `HISTORY BRIEF` to see the list of commands it can perform.

## ⛏️ Built Using <a name = "built_using"></a>

- [C](http://www.open-std.org/jtc1/sc22/wg14/) - C Language
- [Valgrind](https://valgrind.org/) - Valgrind instrumentation framework

## ✍️ Authors <a name = "authors"></a>

- [@mayank-pq2q4](https://github.com/mayank-pq2q4)

See also the list of [contributors](https://github.com/mayank-pq2q4/LAB4/graphs/contributors) who participated in this project.
## The code will be merged after wed: 1800 hours
