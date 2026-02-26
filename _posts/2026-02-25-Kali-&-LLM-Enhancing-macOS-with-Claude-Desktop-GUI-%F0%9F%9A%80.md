---
title: Kali & LLM Enhancing macOS with Claude Desktop GUI 🚀
date: 2026-02-25
categories: [TECHNOLOGY]
tags: [KALI,MACOS,LLM,ANTHROPIC,GUI]
---

## Kali & LLM - macOS with Claude Desktop GUI

This post will focus on an alternative method of using Kali Linux, moving beyond direct terminal command execution. Instead, we will leverage a **Large Language Model (LLM)** to translate natural language descriptions of desired actions into technical commands. Achieving this setup requires the integration of three distinct systems:

- **UI**: Apple’s macOS - with Claude Desktop
- **Attacking box**: Kali Linux - using various tools
- **LLM**: In the cloud - Anthropic’s Sonnet 4.5

The LLM is only part of the story. When paired with **Model Context Protocol (MCP)**, it allows/enables the LLM to seamlessly connect with external sources (data, programs/tools, etc.).

At a very high level, we can ask a LLM to do a task via a prompt. For example, one could prompt, “Can you please port scan scanme.nmap.org? If you find a valid web server, check if security.txt exists.” The LLM will understand what was asked and might process it as, “First task, I need to use Nmap/Network Mapper to do a port scan of scanme.nmap.org.” The LLM will then request the MCP to do any action(s), such as “Is Nmap installed? Can I access it?” The MCP will run the request and return results, for instance, executing `$ nmap scanme.nmap.org`. The LLM will process the results as well as show it to end-users, for example, “I found that scanme.nmap.org is up and contains a web server on port 80/TCP & 443/TCP.” If needed, a loop could re-run a command/action again back in the MCP until the prompt has been completed, such as, “Now I need to see if /.well-known/security.txt gives HTTP 200 response.”

There are various reasons for this specific setup, including the desire for a graphical user interface (GUI), which Claude Desktop provides. Claude Desktop is an official product from Anthropic, who is making the model we want to run, but it is not officially supported on Linux. It is also free, at the time of writing. Speed is another factor; having Kali running in the cloud may have greater network connection or be closer to your target, thus speeding things up! To enable interaction, our macOS box will communicate with Kali using SSH. If Kali is in the cloud, SSH is likely pre-setup. If SSH is not set up, `openssh-server` must be installed and the service enabled. On the macOS machine, a public SSH key needs to be generated, for example, using `ssh-keygen`. This public SSH key from macOS is then added to Kali, allowing for key authentication to the `authorized_keys` file on the Kali box (e.g., at IP 192.168.1.30).

To read the complete article see: [Read full article](https://www.kali.org/blog/kali-llm-claude-desktop/)