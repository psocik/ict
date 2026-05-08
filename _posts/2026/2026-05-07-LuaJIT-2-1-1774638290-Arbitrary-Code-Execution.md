---
title: LuaJIT 2.1.1774638290 - Arbitrary Code Execution
date: 2026-05-07
categories: [SECURITY]
tags: [LUAJIT,ARBITRARY CODE EXECUTION,VULNERABILITY,EXPLOIT]
---

## LuaJIT 2.1.1774638290 - Arbitrary Code Execution 🚨

An exploit titled **"LuaJIT 2.1.1774638290 - Arbitrary Code Execution"** was released on **March 29, 2026** by author **TaurusOmar**. This vulnerability targets **LuaJIT 2.1.1774638290** (latest version), verified on **Linux x86-64 (Arch Linux)**. LuaJIT's **Foreign Function Interface (FFI)** provides unrestricted access to native C functions including `syscall()`, `mmap()`, `mprotect()`, and arbitrary shared library loading. When FFI is accessible to untrusted Lua code in embedding scenarios (OpenResty, Redis, game engines, IoT), an attacker can achieve arbitrary code execution with full process privileges including shellcode execution via `mmap(RWX) + ffi.copy() + ffi.cast()`. 

This affects any application embedding LuaJIT 2.1.x without explicitly disabling FFI (`-DLUAJIT_DISABLE_FFI`) or removing it from the sandbox environment before executing untrusted scripts. The vulnerability was verified on LuaJIT 2.1.1774638290 (March 2026) -- the latest version. Attack scenarios include OpenResty/Nginx with user-controlled Lua scripts, Redis with exposed EVAL interface, game engines with Lua modding systems, and IoT devices with Lua scripting interface.

The provided **Proof of Concept (PoC)** demonstrates **"FFI Unrestricted Syscall Access"**. It shows `ffi.C.getpid()` via `dlsym`, noting that **"dlsym resolves libc symbols without restriction"**, and also via direct `syscall(39)`, confirming **"Both channels confirmed active"**. The PoC outlines **ASLR bypass** via `/proc/self/maps` to find the **"libc base"**. Arbitrary command execution is achieved through `ffi.C.system('id')`, demonstrating direct execution of system commands. Most critically, the PoC illustrates shellcode execution via `mmap(RWX)`. This involves mapping an RWX region, copying a specific x86-64 shellcode for `execve('/bin/sh', NULL, NULL)` into it, and then executing the copied shellcode, resulting in the message **"Shellcode written. Executing execve('/bin/sh')..."**.

Mitigation steps are crucial to prevent this arbitrary code execution. Organizations should compile with `-DLUAJIT_DISABLE_FFI` or remove 'ffi' from the sandbox environment table. Additionally, applying OS-level restrictions such as **seccomp-bpf**, **AppArmor**, or **namespaces** is recommended.

[Read full article](https://www.exploit-db.com/exploits/52554)