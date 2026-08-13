---
title: Linux Kernel Process Accounting
date: 2026-08-12
categories: [TECHNOLOGY]
tags: [LINUX,KERNEL,PROCESS,ACCOUNTING]
---

## Linux Kernel Process Accounting

Process accounting is a kernel feature that allows for the logging of process data. Instead of a specific process managing this, the **accton** command signals the kernel to start logging data to a designated location, typically `/var/log/account/pacct`. Once a process terminates, the kernel logs the respective details into a binary log file. While it does introduce some overhead, many users may hesitate to use it due to the additional disk writes required for collecting information. However, memory and other CPUs should not be significantly impacted by process accounting. On a moderately busy Proxmox system, it consumes about **50 MB/day** of disk space.

### Installation

To install process accounting, simply install the respective package for your distribution. For Debian-based distributions, you can use:

```bash
APT install acct
```

This typically configures the startup scripts automatically, but you can also run:

```bash
systemctl enable --now acct
```

Logs are saved in a binary format, and you can use the **lastcomm** command to display the log in a readable format. This logs the process name, flags (S=super user, F=forked process, D=generated core dump, X=terminated by signal), user name (or ID), CPU execution time, and the timestamp when the process started.

### Log Management

Unlike most Linux logs, these logs are not created by syslog. However, you can still read them with syslog to forward them to a central log collector/SIEM. For example, **syslog-ng** includes a `s_pacct` processor for process accounting logs. The **sa** command can be used to easily extract summaries from accounting data, such as a breakdown by CPU time used by different processes.

### Important Considerations

Process accounting is a kernel feature, and the kernel must be compiled and configured to support it. If you are running Linux containers, process accounting will not work unless the container is privileged. However, the container processes are logged by the host, which is beneficial as it allows for easier centralization of logs, preventing tampering from within the container.

Linux kernel process accounting is a valuable yet often overlooked feature. It does not log command line options, which could be a limitation in incident response. Nevertheless, it serves as a great supplement to other features like **bash_history** files, capturing processes that bash_history would miss.

For more details, you can read the complete article [here](https://isc.sans.edu/forums/diary/Linux%20Kernel%20Process%20Accounting/33240/).