# Linux Fundamentals 2

## Overview

Linux Fundamentals 2 focuses on user accounts, permissions, processes, networking, and basic system administration.

Understanding these concepts is important for both Linux administration and cybersecurity investigations.

## Users

Linux systems use user accounts to control access to files, processes, and system resources.

The root user has the highest level of privileges on a Linux system.

Regular users have more limited permissions.

## `whoami`

`whoami` displays the username of the currently logged-in user.

```bash
whoami
```

This is useful when working with multiple accounts or remote systems.

## `id`

`id` displays information about the current user, including:

* User ID (UID)
* Group ID (GID)
* Group memberships

```bash
id
```

## File Permissions

Linux uses permissions to control access to files and directories.

The three main permission types are:

* `r` — Read
* `w` — Write
* `x` — Execute

Permissions apply to three categories:

* User/Owner
* Group
* Others

Example:

```text
-rwxr-xr--
```

This can be interpreted as:

```text
Owner:  rwx
Group:  r-x
Others: r--
```

## `chmod`

`chmod` changes file and directory permissions.

Example:

```bash
chmod +x script.sh
```

This gives the file execute permission.

Permissions can also be represented numerically.

For example:

```bash
chmod 755 script.sh
```

Common values:

* `4` = Read
* `2` = Write
* `1` = Execute

The values can be combined.

## `chown`

`chown` changes the owner of a file or directory.

```bash
chown user file.txt
```

It can also change the owner and group:

```bash
chown user:group file.txt
```

## Processes

A process is a running instance of a program.

Linux provides several commands for viewing and managing processes.

### `ps`

`ps` displays information about running processes.

```bash
ps
```

A commonly used option is:

```bash
ps aux
```

This provides information about processes running on the system.

### `top`

`top` provides a real-time view of running processes and system resource usage.

```bash
top
```

It can show information such as:

* CPU usage
* Memory usage
* Process IDs
* Running processes

### Process IDs

Each running process has a Process ID (PID).

The PID can be used when managing or investigating processes.

## `kill`

`kill` sends a signal to a process.

Example:

```bash
kill 1234
```

The number represents the PID of the process.

## Networking

Linux systems commonly include tools for inspecting network configuration and connectivity.

### `ip`

The `ip` command can display and configure network information.

```bash
ip addr
```

This can show network interfaces and IP addresses.

### `ping`

`ping` tests network connectivity to another host.

```bash
ping 10.10.10.10
```

It uses ICMP echo requests and replies to test connectivity.

### `ss`

`ss` displays information about network sockets.

```bash
ss -tuln
```

This can be useful for identifying listening network services.

## `netstat`

`netstat` is an older networking utility that can also display network connections and listening services.

On modern Linux systems, `ss` is generally preferred.

## Root and `sudo`

`sudo` allows an authorized user to execute commands with elevated privileges.

Example:

```bash
sudo command
```

Administrative privileges should be used carefully because privileged commands can make significant system changes.

## `/etc/passwd`

The `/etc/passwd` file contains information about local user accounts.

It does not normally contain users' actual password hashes.

Example structure:

```text
username:x:UID:GID:comment:home:shell
```

## `/etc/shadow`

`/etc/shadow` stores password-related information for local accounts.

Access to this file is restricted because it contains sensitive authentication data.

## Key Takeaways

* Linux uses users and groups to manage access.
* Root has the highest level of privileges.
* `whoami` identifies the current user.
* `id` displays UID, GID, and group membership.
* Linux permissions use read, write, and execute permissions.
* `chmod` modifies permissions.
* `chown` changes ownership.
* `ps` and `top` can be used to inspect running processes.
* Processes have unique PIDs.
* `ip` can display network configuration.
* `ping` tests network connectivity.
* `ss` can show listening sockets and network connections.
* `sudo` provides controlled privilege elevation.
* `/etc/passwd` contains local account information.
* `/etc/shadow` contains sensitive password-related information.

## Skills Developed

* Linux user and group management concepts
* File permission analysis
* Process monitoring
* Basic network investigation
* Privilege management
* Linux system administration fundamentals
