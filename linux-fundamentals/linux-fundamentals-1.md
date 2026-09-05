# Linux Fundamentals 1

## Overview

Linux Fundamentals 1 introduces the Linux operating system, the Linux command line, the filesystem, and basic terminal commands.

The command line is an important skill in cybersecurity because many security tools and servers are operated through a terminal.

## Linux

Linux is an open-source operating system kernel used by many operating systems and distributions.

Examples of Linux distributions include:

* Ubuntu
* Debian
* Kali Linux
* Fedora
* Arch Linux

Linux is widely used in servers, cloud environments, networking, and cybersecurity.

## The Linux Terminal

The terminal provides a command-line interface (CLI) for interacting with the operating system.

Instead of using a graphical interface, commands can be entered directly to perform tasks.

## Basic Commands

### `pwd`

`pwd` stands for **Print Working Directory**.

It displays the current directory.

```bash
pwd
```

### `ls`

`ls` lists files and directories in the current directory.

```bash
ls
```

Useful options include:

```bash
ls -l
ls -h
ls -la
```

* `-l` displays detailed information.
* `-h` displays human-readable file sizes.
* `-a` includes hidden files.

### `cd`

`cd` stands for **Change Directory**.

It is used to move between directories.

```bash
cd /etc
```

To move to the parent directory:

```bash
cd ..
```

To return to the home directory:

```bash
cd ~
```

### `cat`

`cat` can be used to display the contents of a file.

```bash
cat file.txt
```

It is useful for quickly reading text files from the terminal.

### `find`

`find` searches for files and directories.

Example:

```bash
find / -name file.txt
```

It can be useful when looking for specific files on a system.

### `grep`

`grep` searches text for a specific pattern.

Example:

```bash
grep "password" file.txt
```

It is commonly used when analysing configuration files, logs, and command output.

### `echo`

`echo` prints text to the terminal.

```bash
echo "Hello"
```

It can also be used with redirection to create or modify files.

## File and Directory Navigation

Linux uses a hierarchical filesystem.

Important directories include:

| Directory | Purpose                               |
| --------- | ------------------------------------- |
| `/`       | Root of the filesystem                |
| `/home`   | User home directories                 |
| `/etc`    | System and application configuration  |
| `/tmp`    | Temporary files                       |
| `/var`    | Variable data such as logs            |
| `/bin`    | Essential commands                    |
| `/usr`    | User-space applications and utilities |
| `/root`   | Home directory of the root user       |

## File Paths

Linux supports absolute and relative paths.

### Absolute Path

An absolute path starts from the root directory.

```text
/etc/passwd
```

### Relative Path

A relative path starts from the current working directory.

```text
documents/file.txt
```

## Command Operators

Linux commands can be combined using operators.

### `>`

Redirects output into a file and overwrites existing content.

```bash
echo "Hello" > file.txt
```

### `>>`

Appends output to an existing file.

```bash
echo "Another line" >> file.txt
```

### `&`

Runs a command in the background.

```bash
command &
```

## Getting Help

Linux provides several ways to learn how commands work.

### `man`

`man` displays the manual page for a command.

```bash
man ls
```

Manual pages are useful when learning command options and syntax.

## File Types

Linux treats many things as files.

The `file` command can be used to identify the type of a file.

```bash
file example.txt
```

## Key Takeaways

* Linux is widely used in servers, cloud environments, and cybersecurity.
* The terminal provides a command-line interface for interacting with Linux.
* `pwd` shows the current directory.
* `ls` lists files and directories.
* `cd` changes directories.
* `cat` displays file contents.
* `find` searches for files and directories.
* `grep` searches text for patterns.
* `echo` prints text.
* `/etc` contains important configuration files.
* `>` overwrites a file while `>>` appends to it.
* `man` provides documentation for commands.
* Absolute paths start from `/`, while relative paths start from the current directory.

## Skills Developed

* Linux filesystem navigation
* Basic command-line usage
* File and directory searching
* Text searching
* Reading configuration files
* Understanding Linux paths
* Using command documentation
