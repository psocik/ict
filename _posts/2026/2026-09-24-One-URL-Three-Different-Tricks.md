---
title: One URL, Three Different Tricks
date: 2026-09-24
categories: [SECURITY]
tags: [PHISHING,URL,SECURITY,TRICKS]
---

## One URL, Three Different Tricks

Yesterday, we received a phishing email with an interesting link. At first sight, it looks like garbage, but every piece of it has been carefully crafted to confuse basic security controls. The defanged link provided was: hxxps://YKZjqa7A@gynd--[.]koncar-hr[.]com/handlers@isc.sans.edu.

### The First Trick
The first trick is the old "userinfo" field. According to RFC 3986, everything between the scheme and an "@" inside the authority is treated as credentials ("user:password@host"). Browsers silently ignore it, but it has two advantages for the attacker. The random string ("YKZjqa7A") makes every URL unique, which defeats exact-match blocklists and URL reputation lookups. It probably also acts as a tracking token per victim or campaign. As a side effect, the whole thing now looks like an email address to any tool that doesn't parse URLs strictly.

### The Second Trick
The second trick is the hostname itself: "gynd--.koncar-hr.com". Per the classic hostname rules (RFC 952/1123), a label can't start or end with a hyphen. DNS doesn't care, and browsers happily resolve and visit it. However, strict validators, regex-based URL extractors, and some link-rewriting or sandboxing solutions may consider it invalid and simply skip it. A URL that is never extracted is never scanned. The random subdomain also suggests wildcard DNS, so each victim gets a brand-new hostname that no blocklist knows. Additionally, the parent domain is a lookalike of the legitimate "koncar.hr" (a Croatian industrial group), with the ccTLD turned into a hyphenated ".com".

### The Last Trick
The last trick is the victim's email address, appended in the path. This is common with phishing kits: the page reads the path, pre-fills the login form with the victim's address, and sometimes adapts the branding to the email domain. There is another benefit, though. A poorly written parser that splits the string on the _last_ "@" will conclude that the host is "isc.sans.edu", the recipient's own trusted domain! Per the WHATWG URL standard, the authority ends at the first "/", so the browser correctly connects to the attacker's server.

### Conclusion
The result is a single string that tells three different stories. A naive filter sees two email addresses or a link to your own domain. A strict validator sees an invalid hostname and drops it. The browser sees a perfectly valid URL and takes the victim straight to the phishing page. Attackers aren't exploiting a vulnerability here but the differences between parsers. For detection, if you want to hunt for this kind of link, look for URLs with more than one "@", hostname labels starting or ending with a hyphen, and paths containing the recipient's own email address.

[Read full article](https://isc.sans.edu/forums/diary/One%20URL,%20Three%20Different%20Tricks/33366/) 
