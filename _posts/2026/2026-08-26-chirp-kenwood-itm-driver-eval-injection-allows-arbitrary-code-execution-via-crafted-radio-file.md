---
title: CHIRP Kenwood ITM Driver Eval Injection Allows Arbitrary Code Execution via Crafted Radio File
date: 2026-08-26
categories: [SECURITY]
tags: [CHIRP,VULNERABILITY,ARBITRARY CODE EXECUTION,SECURITY]
---

## CHIRP Kenwood ITM Driver Eval Injection Vulnerability 🚨

An **eval injection** vulnerability has been discovered in the Kenwood ITM file format driver of **CHIRP**, an open-source application for programming amateur radios. This flaw allows an attacker to execute arbitrary Python code by persuading a user to open a crafted radio file. The affected path is reached through the ordinary **File -> Open** flow in a standard installation, with no dialog or confirmation preceding execution.

### Vulnerability Details 🔍

- **CVSS Score:** 7.8 (AV:L/AC:L/PR:N/UI:R/S:U/C:H/I:H/A:H)
- **NotCVE ID:** NotCVE-2026-0013
- **Affected Builds:** CHIRP chirp-next builds up to and including chirp-next-20260814

The issue arises from the `ITMRadio._clean_tmode()` function in `chirp/drivers/kenwood_itm.py`, which reads two CSV fields, `TXSIG` and `RXSIG`, from the file being opened and passes them directly to Python's built-in `eval()`. This means any Python expression placed in either field is evaluated at file-load time, leading to potential exploitation.

### Attack Vectors ⚠️

While the `.itm` extension is not offered by the default filter in the Open dialog, an attacker can use a second variant. By embedding the same CSV payload in a `.img` file with a trailing CHIRP metadata blob, the driver can still be selected, allowing for exploitation.

### Mitigation 🛡️

The vulnerability was reported to the CHIRP maintainer on **August 17, 2026**, and was fixed the same day. The fix removes the `eval()` calls and replaces them with a safer parsing method. The findings were published as NotCVE-2026-0013 on **August 22, 2026**.

For more details, you can read the complete article here: [Read full article](https://seclists.org/fulldisclosure/2026/Aug/114)