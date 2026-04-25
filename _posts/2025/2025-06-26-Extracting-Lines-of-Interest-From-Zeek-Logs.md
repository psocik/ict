---
title: Extracting Lines of Interest From Zeek Logs
date: 2025-06-26
categories: [RESEARCH]
tags: [ZEEK,LOGS,DNS,SECURITY]
---

## Overview
Imagine that you’re looking at a potential issue that shows up in a Zeek log file. Instead of attaching the entire log file to a response ticket it might make sense to extract just the lines relevant to this issue and attach just those lines to save space – and not share something else that might need to stay private!

In the following examples we’ll assume that the relevant DNS traffic is between local system 10.0.0.14 and remote system 8.8.8.8 (one of Google’s public DNS servers).

## Steps
We need to 1) make a temporary directory to accept the new logs files, 2) for each log get all the raw lines from the existing logs, and 3) request the lines of interest and all the headers. We also need to save this output to a brand new file in the temporary directory.

To read the complete article see: [Extracting Lines of Interest From Zeek Logs](https://www.activecountermeasures.com/extracting-lines-of-interest-from-zeek-logs/)
