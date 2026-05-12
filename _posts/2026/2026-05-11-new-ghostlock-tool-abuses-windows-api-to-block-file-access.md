---
title: New GhostLock Tool Abuses Windows API to Block File Access
date: 2026-05-11
categories: [SECURITY]
tags: [GHOSTLOCK,WINDOWS,API,SECURITY,FILE-ACCESS]
---

## New GhostLock Tool Abuses Windows API to Block File Access 🚀

A security researcher has released a proof-of-concept tool named **GhostLock** that demonstrates how a legitimate Windows file API can be abused in attacks to block access to files stored locally or on SMB network shares. This technique, created by Kim Dvash of Israel Aerospace Industries, abuses the Windows 'CreateFileW' API and file-sharing modes to prevent other users and applications from opening files while handles remain active.

The GhostLock technique abuses the 'dwShareMode' parameter in the CreateFileW() function, which specifies the type of access other processes have to a file while it is opened. When a file is opened with `dwShareMode = 0`, Windows grants the process exclusive access to the file, preventing other users or applications from opening it. The researcher has published a GhostLock tool on GitHub that automates this attack by recursively opening a large number of files on SMB shares. While these file handles are open, new attempts to access the files will fail with sharing violations, with Windows displaying a 'STATUS_SHARING_VIOLATION' error.

The tool can be run by "standard" domain users and does not need any elevated privileges to lock files. However, once the associated SMB session is terminated, the GhostLock processes are killed, or the affected system is rebooted, Windows automatically closes the handles, and access to the files is restored. Dvash told BleepingComputer that the technique should be viewed primarily as a disruption attack rather than a destructive one, like ransomware. **"Yes, the impact is disruption-based, not destructive. The parallel to ransomware is the operational downtime window, not data loss,"** Dvash told BleepingComputer.

While this attack is more akin to a denial-of-service technique, it could be useful as a decoy during intrusions. Attackers could use widespread file-access disruptions to overwhelm IT staff while conducting data theft, lateral movement, or other malicious activity elsewhere in the environment.

The researcher says that many security products and behavioral detection systems focus on detecting mass file writes or encryption operations. GhostLock primarily generates large numbers of legitimate file open requests, making it less likely to be detected. **"The only observable that reliably identifies this attack is the per-session open-file count with ShareAccess = 0 at the file server layer -- a metric that lives inside storage platform management interfaces, not in Windows event logs, not in EDR telemetry, not in network flow data,"** explains Dvash.

To read the complete article see:
[Read full article](https://www.bleepingcomputer.com/news/security/new-ghostlock-tool-abuses-windows-api-to-block-file-access/)