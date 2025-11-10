---
title: Dangerous runC flaws could allow hackers to escape Docker containers
date: 2025-11-09
categories: [SECURITY]
tags: [DOCKER,CYBERSECURITY,VULNERABILITIES]
---

Three newly disclosed vulnerabilities in the runC container runtime used in Docker and Kubernetes could be exploited to bypass isolation restrictions and get access to the host system.

An attacker exploiting the vulnerabilities could obtain write access to the underlying container host with root privileges: CVE-2025-31133 — runC uses /dev/null bind-mounts to “mask” sensitive host files. If an attacker replaces /dev/null with a symlink during container init, runC can end up bind-mounting an attacker-controlled target read-write into the container — enabling writes to /proc, and container escape.

CVE-2025-31133 and CVE-2025-52881 affect all versions of runC, while CVE-2025-52565 impacts runC versions 1.0.0-rc3 and later. Fixes are available in runC versions 1.2.8, 1.3.3, 1.4.0-rc.3, and later.

RunC developers also shared mitigation actions, which include activating user namespaces for all containers without mapping the host root user into the container's namespace. This precaution should block the most important parts of the attack because of the Unix DAC permissions that would prevent namespaced users from accessing relevant files.

To read the complete article, see: [Bleeping Computer](https://www.bleepingcomputer.com/news/security/dangerous-runc-flaws-could-allow-hackers-to-escape-docker-containers/).