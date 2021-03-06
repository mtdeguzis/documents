<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [About](#about)
- [Terminology](#terminology)
- [IDE (GUI-based)](#ide-gui-based)
- [CLI](#cli)
  - [gdb](#gdb)
  - [strace](#strace)
- [General guidelines](#general-guidelines)
- [Links](#links)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# About
Some notes about debugging

# Terminology

* **Step Into** - A method is about to be invoked, and you want to debug into the code of that method, so the next step is to go into that method and continue debugging step-by-step.
* **Step Over** - A method is about to be invoked, but you're not interested in debugging this particular invocation, so you want the debugger to execute that method completely as one entire step.
* **Step Return** - You're done debugging this method step-by-step, and you just want the debugger to run the entire method until it returns as one entire step.
* **Resume** - You want the debugger to resume "normal" execution instead of step-by-step
* **Line Breakpoint** - You don't care how it got there, but if execution reaches a particular line of code, you want the debugger to temporarily pause execution there so you can decide what to do.

# IDE (GUI-based)

* ATOM - many languages (text based)
* Bluefish - ASP .NET, C/C++, CSS, HTML5, JavaScript and jQuery, Java, Pearl, PHP, 
* CodeLite - C and C++ (text based)
* Eclipse - Java, C, C++, PHP, Python, Perl, Ruby and more.
* Komodo IDE - PHP, Ruby, Perl, Python, Node.js
* MonoDevelop - VB, Java, C/C++, C#, Python
* Netbeans - Java, Python, C/C++, Ruby, PHP, JavaScript etc.
* Sublime Text - All major languages (text based)

# CLI
 
 * gdb
 * strace
 
## gdb

 * [Debugging with GDB (large manual)](http://www.sourceware.org/gdb/download/onlinedocs/gdb.html)
 * [General overview](https://www.chemie.fu-berlin.de/chemnet/use/info/gdb/gdb_5.html)
 * [gdb backtrace](https://sourceware.org/gdb/onlinedocs/gdb/Backtrace.html)

## strace

```
strace -fp $(pidof -s steam) -e file -t
```

# General guidelines

* [Arch Linux wiki](https://wiki.archlinux.org/index.php/Step-by-step_debugging_guide)

# Links

* [Nice list of IDEs](http://codecondo.com/10-best-ides-linux/)
