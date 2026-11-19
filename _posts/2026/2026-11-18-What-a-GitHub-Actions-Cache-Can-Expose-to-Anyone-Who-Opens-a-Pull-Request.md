---
title: What a GitHub Actions Cache Can Expose to Anyone Who Opens a Pull Request
date: 2026-11-18
categories: [SECURITY]
tags: [GITHUB,ACTIONS,CACHE,SECURITY,CREDENTIALS]
---

## What a GitHub Actions Cache Can Expose to Anyone Who Opens a Pull Request

The **GitHub Actions cache** is commonly used as a timesaver. While praiseworthy, it can create a loophole for malicious actors to exploit. GitHub allows pull request runs to restore caches from the base branch, including from forks. If you're running a public repository, anyone can create a fork and read whatever has been cached on the main branch. Even with private repositories, anyone with read access can run the same stunt.

### The Risks of Cached Secrets

The problem arises when people are careless about what gets stored in cached paths. A pull request with no access to secrets can still read them if those credentials are bundled together in a cache. This is not just a theoretical danger; the **GhostAction campaign** showed how attractive CI credentials are. Attackers read projects' existing workflow files to learn which secrets they used, then committed malicious workflows with those secret names hardcoded to steal them.

GitHub is clear that anyone with read access to a repository can create a pull request and access the content of a cache. It's equally open in warning users that forks can create pull requests and access caches on a base branch. Safeguards are in place, but they do not limit reading. If secrets have been written into a cached path on the main branch, a fork's workflow can restore them without ever having access to the secrets themselves.

### Best Practices for Caching

Keeping secrets out of GitHub Actions caches is a long-known best practice. Secrets can end up in caches unintentionally, especially when cache paths are too broad, like caching the entire home directory or the full workspace. For example, the `docker login` command saves registry credentials to `~/.docker/config.json`, and cloud command-line tools store credentials locally (e.g., AWS CLI in `~/.aws`). API keys, passwords, and other environment variable values can be stored in `.env` files or embedded in build outputs and cached by mistake.

GitHub regularly clears out cache entries; anything not accessed for seven days gets deleted. However, this is not the same as removing credentials. If a pull request restores a cache, the credentials come along with it and can be copied anywhere. These credentials are most likely still active and effective. One recent report found that **64% of valid secrets from 2022 were still not revoked in 2026**.

### Recommendations

The best protection is to stop any credentials from getting cached. Only relevant folders should be cached, such as dependencies and build outputs. Complete home directories and workspaces should never be cached. Good housekeeping habits like logging out and clearing credentials before caching can help. **OpenID Connect (OIDC)** provides temporary cloud credentials instead of long-lasting access keys that can be exploited by pull requests.

Additionally, set external contributors to require manual approval for workflows. Regularly review caches for secrets that might have been exposed and replace those credentials before deleting the unsafe cache. The safe working assumption is that every cached path is readable by anyone who can open a pull request. Decide what goes into the cache on that basis, and keep credentials out of it.

[Read full article](https://hackread.com/what-github-actions-cache-expose-to-pull-request/) 