---
title: Linux Shell Forensic Let's Dive Into Atuin!
date: 2026-08-07
categories: [FORENSICS]
tags: [LINUX,FORENSICS,ATUIN,SHELL]
---

## Linux Shell Forensic: Let's Dive Into Atuin!  

**Source:** SANS ISC  
**Date Published:** August 7, 2026  

UNIX systems (including Linux) are well-known for recording a lot of activities in various locations. However, one area where they lack modern logging is in shells. Most shells provide a history of typed commands through a flat file in the `$HOME` directory (e.g., `$HOME/.bash_history`). Unfortunately, they suffer from several issues:  
- History is stored in memory and the file is updated only when the shell exits.  
- The order of commands is not reliable.  
- There are no timestamps (by default).  
- The size of history can be limited.  

Fortunately, there are tools that enhance the power of reverse-i-search and shell history by storing everything in a database. One popular tool is **Atuin**. It enhances your shell history with a SQLite database and records extra context for every command:  
- The directory it ran in  
- How long it took  
- Whether it succeeded  
- Which machine and session it came from  

From a forensic perspective, this tool can be both a gift and a trap for investigators. If you are unaware that Atuin is being used, you might lose a lot of evidence. However, if you spot it, it can be a significant advantage!  

### First Step: Check Where the Artifacts Live  
Atuin follows XDG paths, so check every user's home directory plus root (for per-user installs). The primary evidence is located at `~/.local/share/atuin/history.db` (SQLite), alongside `~/.local/share/atuin/history.db-wal` for uncommitted records. Other relevant files include:  
- `~/.local/share/atuin/key`  
- `~/.local/share/atuin/session`  
- `~/.config/atuin/config.toml` for configuration  

Do not assume the default location. The config location can be overridden with `$ATUIN_CONFIG_DIR`, and the database, key, and session paths are all individually configurable in `config.toml`. It is recommended to read the config first. Atuin must be enabled at the shell level (for every shell, every user). Search for proof of activation in the shell RC files, for example, `eval "$(atuin init bash)"`.  

### Second Step: Build Your Timeline  
The main DB table is called **history**. The schema for this table includes:  
- `id` text primary key  
- `timestamp` integer not null  
- `duration` integer not null  
- `exit` integer not null  
- `command` text not null  
- `cwd` text not null  
- `session` text not null  
- `hostname` text not null  

Compared to `.bash_history`, this gives you, per command:  
- A UTC timestamp (nanoseconds since epoch -- divide by 1e9)  
- The working directory  
- The exit code  
- Execution duration  
- A session ID  
- The hostname  

An interesting query example is:  
`SELECT datetime(timestamp/1000000000,'unixepoch') AS utc, hostname, session, cwd, exit, command FROM history ORDER BY timestamp;`  

### Next Step: Investigate Deleted and Residual Data  
The "soft-delete" design means rows deleted via Atuin are marked with "deleted_at" rather than physically purged in many cases. Investigators can try to use `WHERE deleted_at IS NOT NULL` to recover "deleted" activity. Standard SQLite carving applies, as freelist/unallocated pages and the WAL can hold prior row versions and dropped records. The standard flat history file (`~/.bash_history` or `~/.zsh_history`) is still written alongside Atuin, so cross-reference it.  

[Read full article](https://isc.sans.edu/forums/diary/Linux%20Shell%20Forensic:%20Let%3Fs%20Dive%20Into%20Atuin!/33226/)