<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [About](#about)
- [What is swap space?](#what-is-swap-space)
- [Why Swapoff is So Darned Slow](#why-swapoff-is-so-darned-slow)
- [Analyzign Swap Usage](#analyzign-swap-usage)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# About

General notes on Linux swap

# What is swap space?

Linux divides its physical RAM (random access memory) into chucks of memory called pages. Swapping is the process whereby a page of memory is copied to the preconfigured space on the hard disk, called swap space, to free up that page of memory. The combined sizes of the physical memory and the swap space is the amount of virtual memory available.

Swapping is necessary for two important reasons. First, when the system requires more memory than is physically available, the kernel swaps out less used pages and gives memory to the current application (process) that needs the memory immediately. Second, a significant number of the pages used by an application during its startup phase may only be used for initialization and then never used again. The system can swap out those pages and free the memory for other applications or even for the disk cache.

Source: [Linux.com](https://www.linux.com/news/all-about-linux-swap-space)

# Why Swapoff is So Darned Slow

Most people who’ve installed Linux are familiar with the idea of a swap partition. That odd little slice of the hard disk that you can’t use for a drive. The kernel’s virtual memory system uses it as an overflow tank for RAM (it gets used for other things, too, such as when you put your computer into hibernation). Most personal computers only have one, but there can actually be up to 32 of them.

Occasionally, a system administrator might need to take one offline. That’s what the swapoff command does. At any given time, an active swap partition will be holding any number of memory pages; and before it’s deactivated, all those pages will need to be swapped back into RAM, and the page tables of the programs that are using them will have to be updated so that the programs can find them. It sounds like it should be easy, given enough free RAM to hold them all, but many of them are being used by more than one program. Think of the program that draws your window buttons on the screen, for instance. Instead of writing that program into RAM over and over and taking up a lot of room, all the programs that need a window can use the same copy of it.

The way it works now, swapoff looks at each swapped out memory page in the swap partition, and tries to find all the programs that use it. If it can’t find them right away, it will look at the page tables of every program that’s running to find them. In the worst case, it will check all the page tables for every swapped out page in the partition. That’s right–the same page tables get checked over and over again. This is a huge waste of effort. One user said it took over four hours for swapoff to run.

Source: [salticidoftheearth](https://salticidoftheearth.com/2014/01/09/why-swapoff-is-so-darned-slow/)

# Analyzign Swap Usage

Type the following bash for loop command to see swap space usage per process:

```
## bash for loop ##
for file in /proc/*/status ; do awk '/VmSwap|Name/{printf $2 " " $3}END{ print ""}' $file; done
```

Type the following command to sort out output:
```
## Get swap space in Linux using bash for loop ##
for file in /proc/*/status ; do awk '/VmSwap|Name/{printf $2 " " $3}END{ print ""}' $file; done | sort -k 2 -n -r | less
```

Sample outputs:
```
php-cgi 11964 kB
php-cgi 11016 kB
php-cgi 10392 kB
php-cgi 10336 kB
php-cgi 9844 kB
php-cgi 9780 kB
php-cgi 8584 kB
php-cgi 7996 kB
php-cgi 7960 kB
php-cgi 7956 kB
php-cgi 7796 kB
php-cgi 7540 kB
php-cgi 6884 kB
squid 6864 kB
php-cgi 6640 kB
php-cgi 6556 kB
php-cgi 5848 kB
php-cgi 5744 kB
php-cgi 5636 kB
php-cgi 5592 kB
php-cgi 5488 kB
php-cgi 5132 kB
php-cgi 4584 kB
php-cgi 4508 kB
php-cgi 4388 kB
lighttpd 4100 kB
php-cgi 3984 kB
php-cgi 3644 kB
php-cgi 3616 kB
php-cgi 3604 kB
rpc.mountd 3580 kB
....
```

Source: https://www.cyberciti.biz/faq/linux-which-process-is-using-swap/
