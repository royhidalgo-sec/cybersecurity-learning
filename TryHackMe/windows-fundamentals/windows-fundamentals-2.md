# Windows Fundamentals 2

## Overview

Windows Fundamentals 2 focuses on Windows utilities used for system administration, configuration, monitoring, and troubleshooting.

It also introduces the Windows Registry and Windows services.

## System Information

`msinfo32` opens System Information.

It provides detailed information about:

* Hardware
* System components
* Software environment
* Operating system configuration

## System Configuration

`msconfig` opens System Configuration.

It can be used to troubleshoot and configure:

* Startup options
* Boot configuration
* Windows services
* System startup behavior

## Environment Variables

Environment variables store information used by Windows and applications.

For example:

```text
%WINDIR%
```

points to the Windows installation directory.

Other common environment variables include:

```text
%TEMP%
%PATH%
```

## Computer Management

`compmgmt.msc` opens Computer Management.

It provides access to several administrative tools, including:

* Event Viewer
* Task Scheduler
* Local Users and Groups
* Performance
* Device Manager
* Disk Management
* Services

## Event Viewer

`eventvwr.msc` opens Event Viewer.

Event Viewer is used to inspect Windows event logs.

Logs can contain information about:

* System events
* Application events
* Security events
* Errors
* Warnings
* Authentication activity

Event Viewer is particularly useful for troubleshooting and security investigations.

## Resource Monitor

`resmon` opens Resource Monitor.

It provides detailed information about:

* CPU
* Memory
* Disk
* Network

Resource Monitor provides more detailed information than Task Manager for investigating system resource usage.

## Windows Registry

The Windows Registry is a hierarchical database that stores configuration information for:

* Windows
* Users
* Applications
* Hardware

The Registry is organized into keys and values.

### Registry Editor

`regedit` opens the Registry Editor.

The Registry Editor allows administrators to view and modify Registry keys and values.

### Important distinction

The **Registry** is the configuration database.

`regedit` is the **tool used to access and modify the Registry**.

## Windows Services

Windows services are background processes that perform specific system or application functions.

Services can be managed using:

```text
services.msc
```

Services can be configured to start automatically, manually, or be disabled.

## Key Takeaways

* `msinfo32` provides detailed system information.
* `msconfig` is useful for system configuration and troubleshooting.
* `compmgmt.msc` provides access to multiple administrative tools.
* Event Viewer is important for investigating Windows logs.
* Resource Monitor provides detailed resource monitoring.
* The Windows Registry stores important system configuration information.
* `regedit` is the Registry Editor.
* Windows services perform background tasks for the operating system and applications.
