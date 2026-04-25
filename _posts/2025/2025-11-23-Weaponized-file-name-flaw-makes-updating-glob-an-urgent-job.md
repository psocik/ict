---
title: Weaponized file name flaw makes updating glob an urgent job
date: 2025-11-23
categories: [VULNS]
tags: [CVE-2025-64756,GLOB,SECURITY,VULNERABILITY]
---

Researchers are urging users of the glob file pattern matching library to update their installations due to a recently discovered remote code execution flaw (CVE-2025-64756) in the tool's CLI. The vulnerability, rated 7.5, affects versions v10.2.0 through v11.0.3 of glob. Glob is a widely used library for finding files using wildcards, particularly within the JavaScript ecosystem.

The vulnerability lies within glob's CLI tool, specifically the –c flag, which is used to execute commands on matching files. The issue stems from the fact that glob is programmed with shell: true enabled by default. This means that when a file is found using glob's CLI tool with the –c flag, the file's name is passed to a shell for execution. On POSIX systems (Linux, macOS, BSD, etc.), shell metacharacters included in a file name are executed as code. According to AISLE researchers, the implementation assumed filenames were trustworthy data, which turned out to be incorrect.

This vulnerability poses a risk in environments that process files from untrusted sources on POSIX systems, especially those with CI/CD pipelines or build scripts that invoke glob –c or glob –cmd. A maliciously crafted filename, when processed by glob –c, could execute arbitrary code, granting an attacker control over the system. While glob is downloaded millions of times a week, the CLI tool and the –c flag are rarely used, which may explain why the flaw remained unnoticed for so long.

The risk is specific to environments where `glob -c` or `glob -cmd` are used on untrusted files in POSIX systems. Security teams should audit their CI/CD pipelines and build scripts to determine if they use glob in this manner. Users meeting these criteria should immediately update to glob v10.5.0, v11.1.0, or v12.0.0, which contain the fix. This update will prevent malicious filenames from being interpreted as executable code.

[Read the full article here.](https://www.theregister.com/2025/11/23/infosec_news_in_brief/) 