---
title: Cavern Manticore Exposing Iran-Linked Modular C2 Framework
date: 2026-07-06
categories: [CYBERSECURITY]
tags: [CAVERN MANTICORE,IRAN,C2 FRAMEWORK,MALWARE,CYBERSECURITY]
---

## Cavern Manticore: Exposing Iran-Linked Modular C2 Framework

**Source:** Checkpoint Research  
**Date Published:** July 6, 2026  

Since early 2026, Check Point Research (CPR) has tracked a new modular command-and-control framework used by Cavern Manticore, an Iran-nexus APT group primarily targeting Israeli organizations, with a focus on IT providers and government sectors. Cavern Manticore is linked to the Iran MOIS (Ministry of Intelligence and Security) and has connections to the OilRig subgroup named Lyceum. This framework reflects a mature and adaptable toolset built around a shared .NET foundation, utilizing multiple compilation formats. 🚀  

During our investigation, we observed both Cavern agents and modules in the wild, highlighting a modular architecture that separates core communication capabilities from mission-specific post-exploitation functionality. This design allows operators to tailor deployments per victim environment, limit what defenders and analysts can recover from any single victim, and extend access after compromise through specialized modules for reconnaissance, data access, tunneling, and lateral movement.  

Cavern is a modular post-exploitation C2 framework built entirely on .NET, but deliberately compiled into three different binary formats: .NET Framework (IL-only), Mixed-Mode C++/CLI (IL + Native), and .NET 8 NativeAOT (Native-only). The most distinctive architectural decision in Cavern is the deliberate use of three different .NET compilation targets across its components. This is not obfuscation in the traditional sense; there is no packer, no control-flow flattening, and no string encryption anywhere in the framework. Instead, the compilation format itself becomes the anti-analysis layer, since each of the three formats must be reversed with a different toolchain and workflow, requiring analysts to context-switch between them across components.  

The recovered execution chain begins with SysAid's software update feature, which the actor leverages to deploy a WinDirStat DLL sideloading package to `C:\ProgramData\WinDir\WinDirStat.exe`. The legitimate WinDirStat.exe binary loads the trojanized `uxtheme.dll`, which is the Cavern Agent, and the agent in turn loads a dedicated native communication module `n-HTCommp.dll` to reach the C2 and then pulls down additional post-exploitation modules on operator command. The Cavern Agent, compiled as a 64-bit Mixed-Mode C++/CLI DLL named `uxtheme.dll`, exports 83 functions that mimic the legitimate Windows theming library. Of these 83 exports, 82 are empty stubs, with the single live export, `EnableThemeDialogTexture`, serving as the operational entry point for the entire C2 loop. This design creates a deliberate sandbox trap. Any automated analysis tool that invokes ordinal #1, or any other default export, will observe only inert DLL loading behavior and conclude the sample is benign. The real backdoor personality sits entirely behind export ordinal #20 (0x14). Upon invocation, `EnableThemeDialogTexture` creates a singleton mutex, initializes the local configuration from `config.txt`, and enters an infinite polling loop.  

One of the most technically interesting mechanisms in the Cavern Agent is its module hosting strategy. Rather than loading .NET modules into the default AppDomain via `Assembly.Load`, Cavern creates a dedicated AppDomain for each module execution, marshals a proxy object across the domain boundary, invokes the module, and then unloads the entire AppDomain. By isolating each module in its own AppDomain, Cavern achieves two objectives: loaded modules can be cleanly removed from memory after execution, leaving no analyzable assembly artifacts behind, and different versions of the same module can be loaded and run one after another without conflict.  

The native path contains two error strings worth flagging: "What is this sh*t?! where is get_version?!?" and "DLL not found...Maybe you didn't upload it!!!". These are not the kind of polished, neutral diagnostics a code generator tends to emit. They are written in the first person, with frustration, profanity, and exclamation marks.  

[Read full article](https://research.checkpoint.com/2026/cavern-manticore-exposing-iran-linked-modular-c2-framework/)