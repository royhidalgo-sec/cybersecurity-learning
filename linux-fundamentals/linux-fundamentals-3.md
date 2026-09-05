# Linux Fundamentals 3

## Overview

Linux Fundamentals 3 focuses on more practical Linux administration and security concepts, including command-line utilities, services, logs, automation, and basic system investigation.

These skills are particularly useful when working with Linux servers and cybersecurity tools.

## File and Directory Management

Linux provides several commands for managing files and directories.

### `mkdir`

Creates a new directory.

```bash
mkdir directory
```

### `touch`

Creates an empty file or updates the timestamp of an existing file.

```bash
touch file.txt
```

### `cp`

Copies files or directories.

```bash
cp file.txt backup.txt
```

### `mv`

Moves or renames files and directories.

```bash
mv old.txt new.txt
```

### `rm`

Removes files.

```bash
rm file.txt
```

Directories can be removed recursively using:

```bash
rm -r directory
```

Care should be taken with `rm`, especially when using recursive or privileged commands.

## Searching and Filtering

Command-line tools can be combined to efficiently search and analyse information.

### `grep`

Searches for matching text.

```bash
grep "error" logfile.txt
```

### `find`

Searches for files and directories.

```bash
find /var/log -name "*.log"
```

### Pipes

The pipe operator `|` sends the output of one command into another command.

Example:

```bash
ps aux | grep apache
```

This can be useful for filtering command output.

## `wc`

`wc` counts lines, words, and characters.

```bash
wc -l file.txt
```

The `-l` option counts lines.

## `sort`

`sort` sorts lines of text.

```bash
sort file.txt
```

It can be combined with other commands:

```bash
cat file.txt | sort
```

## `uniq`

`uniq` removes or identifies repeated adjacent lines.

It is often combined with `sort`:

```bash
sort file.txt | uniq
```

## Logs

Linux systems store important information in log files.

Many logs can be found under:

```text
/var/log/
```

Examples include logs related to:

* Authentication
* System events
* Applications
* Services
* Kernel activity

Logs are important during troubleshooting and security investigations.

## Processes and Services

Linux systems run background services that provide functionality such as:

* SSH
* Web servers
* DNS
* Databases
* System management

The exact service-management commands can depend on the Linux distribution and init system.

On systems using `systemd`, `systemctl` is commonly used.

### `systemctl`

View the status of a service:

```bash
systemctl status ssh
```

Start a service:

```bash
sudo systemctl start ssh
```

Stop a service:

```bash
sudo systemctl stop ssh
```

## SSH

SSH (Secure Shell) provides encrypted remote access to Linux systems.

A typical SSH connection looks like:

```bash
ssh username@hostname
```

SSH commonly operates over TCP port `22`, although administrators can configure it to use another port.

## Networking Investigation

Network information is important when investigating a Linux system.

Useful commands include:

```bash
ip addr
```

```bash
ip route
```

```bash
ss -tuln
```

These commands can help identify:

* Network interfaces
* IP addresses
* Routing information
* Listening services
* Network connections

## Shell Scripting

Shells can also be used to automate repetitive tasks.

A simple Bash script can contain commands that are executed sequentially.

Example:

```bash
#!/bin/bash

echo "System information"
whoami
pwd
```

The first line specifies the interpreter used to execute the script.

## Shebang

The `#!` sequence at the beginning of a script is called a shebang.

For example:

```bash
#!/bin/bash
```

It tells the system which interpreter should execute the script.

## Executable Scripts

A script needs execute permission to be run directly.

```bash
chmod +x script.sh
```

It can then be executed with:

```bash
./script.sh
```

## Environment Variables

Environment variables provide information to processes and applications.

To display environment variables:

```bash
env
```

To display a specific variable:

```bash
echo $PATH
```

`PATH` contains directories where the shell searches for executable commands.

## Cron

Cron can be used to schedule commands and scripts to run automatically.

Scheduled tasks can be useful for:

* Maintenance
* Backups
* Monitoring
* Automation

From a security perspective, scheduled tasks should also be investigated when looking for persistence mechanisms.

## Command History

Shell history can contain previously executed commands.

For Bash, history can commonly be accessed with:

```bash
history
```

It can be useful during troubleshooting or system investigation, although history should not be treated as a complete audit log.

## Key Takeaways

* Linux provides powerful command-line tools for managing and investigating systems.
* `mkdir`, `touch`, `cp`, `mv`, and `rm` manage files and directories.
* Pipes allow the output of one command to become the input of another.
* `grep`, `find`, `sort`, and `uniq` are useful for searching and analysing text.
* `/var/log/` contains important Linux logs.
* `systemctl` can manage services on systems using systemd.
* SSH provides encrypted remote access to Linux systems.
* `ip`, `ss`, and `ip route` are useful for network investigation.
* Bash scripts can automate repetitive tasks.
* `chmod +x` gives a script execute permission.
* Environment variables influence how commands and applications operate.
* Cron can schedule automated tasks.
* Command history can provide useful investigation context.

## Skills Developed

* Linux command-line proficiency
* File and directory management
* Text processing
* Log investigation fundamentals
* Process and service investigation
* Network troubleshooting
* Bash scripting fundamentals
* Basic Linux security investigation
