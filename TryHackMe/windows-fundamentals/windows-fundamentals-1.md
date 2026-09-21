# Windows Fundamentals 1

## Overview

Windows Fundamentals 1 introduces the Windows operating system, its graphical user interface, file system, user accounts, permissions, User Account Control (UAC), and basic system management tools.

## Windows Desktop

The Windows desktop is the graphical user interface used to interact with the operating system.

Common components include:

* Start Menu
* Taskbar
* Search
* Desktop
* Notification Area
* File Explorer

## NTFS

NTFS (New Technology File System) is the primary file system used by modern Windows systems.

It provides features such as:

* File and folder permissions
* File and folder ownership
* Encryption support
* Compression
* Auditing

### NTFS Permissions

NTFS permissions control what users and groups can do with files and folders.

Common permissions include:

* Read
* Write
* Modify
* Full Control

Permissions can be assigned to individual users or groups.

## Windows Users

Windows supports different types of user accounts with different levels of access.

### Administrator

Administrators can perform system-level actions such as:

* Installing software
* Creating and managing users
* Modifying system settings
* Managing permissions

### Standard User

Standard users have more limited permissions and generally cannot perform administrative actions without elevation.

## User Account Control

UAC (User Account Control) is a Windows security feature designed to prevent unauthorized changes to the operating system.

When an action requires elevated privileges, UAC can request confirmation or administrator credentials.

## Task Manager

Task Manager is a Windows utility used to monitor and manage running processes and system resources.

It can be used to:

* View running processes
* End processes
* Monitor CPU usage
* Monitor memory usage
* View logged-in users
* Manage startup applications

It can be opened with:

```text
taskmgr
```

## Control Panel

Control Panel provides access to various Windows configuration and administration options.

It can be used to manage:

* User accounts
* Network settings
* Programs
* Hardware
* System configuration

## File Explorer

File Explorer is used to navigate and manage files and folders within Windows.

It can be used to:

* Create files and folders
* Move and copy files
* Delete files
* View file properties
* Manage permissions

## System32

`C:\Windows\System32` contains many important Windows system files, executables, and utilities.

System32 is a critical part of the Windows operating system.

## Key Takeaways

* NTFS is the primary Windows file system.
* NTFS permissions control access to files and folders.
* Users and groups can be assigned permissions.
* Administrator and Standard User accounts have different privileges.
* UAC helps protect Windows from unauthorized administrative changes.
* Task Manager can be used to monitor processes and system resources.
* System32 contains critical Windows system files and utilities.
