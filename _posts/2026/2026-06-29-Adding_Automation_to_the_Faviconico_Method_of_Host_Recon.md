---
title: Adding Automation to the Favicon.ico Method of Host Recon
date: 2026-06-29
categories: [SECURITY]
tags: [FAVICON,AUTOMATION,HOST RECON,SECURITY]
---

## Adding Automation to the Favicon.ico Method of Host Recon

The **"favicon.ico"** file is the 16x16 pixel icon that appears in the tab view for any particular host. Many organizations mandate the same file for all of their hosts, which means you can often find hosts that should be in the scope of your engagement but don't show up elsewhere. To get the favicons.ico hash value from a site, this one-liner is the way to go (Windows CMD version shown):

```bash
curl -sL https://%1/favicon.ico | python -c "import sys, base64, mmh3; print(mmh3.hash(base64.encodebytes(sys.stdin.buffer.read())))"
```

Running this for **www.canada.ca**, for example, returns the hash `-1830416802`.

Next, to find other hosts with this hash value, researchers query **Shodan**. From the web interface, one would use:

```bash
http.favicon.hash:-1830416802
```

This gives an unwieldy list of hundreds of hosts, organized by IP address but with a myriad of info for each IP. To obtain a list of hostnames, the **Shodan API** is used. For future engagements, this process can be scripted using the command:

```bash
curl -s -k "https://api.shodan.io/shodan/host/search?key=%APIKEY_SHODAN%&query={http.favicon.hash:%1}"
```

For the example hash, this query returns a HUGE file of 6MB.

From the output file, the goal is to extract the **"hostnames"** arrays into a text list suitable for tools like **nmap**. To query at arbitrary/recursive depth within the data structure, the **".."** query method in **jq** is applied. The command:

```bash
type fa.out | jq -r ".. | arrays[].hostnames?" | more
```

extracts these arrays. To distill this into a plain list, the following command is used to delete brackets, commas, spaces, and quotes, and to remove **"null"** hostnames:

```bash
cat fa.out | jq -r ".. | arrays[].hostnames?" | grep -v null | tr -d ",\"\[\]"
```

Running it all through a standard sort/uniq filter gives a final list of hostnames.

The final hostname count obtained from this method was **363**. While a few false positives and hostnames duplicated with a **"www."** prefix were observed, the list was largely accurate. With a few manual edits, this gives a sorted list of hostnames that can be used for **nmap** or whatever tool; for instance:

```bash
nmap -sT -p443 --open --resolve-all -iL fav.out
```

The **363 hostnames** resolved out to **373 IP addresses**. To obtain a more useful list by finding all open ports on these target hosts (using the IP addresses, not the fqdn hostnames), **masscan** can be employed:

```bash
masscan -sT -p0-65535 --rate 2500 --open -iL fav.out | tee tcp-open-ports.out
```

This scan discovered **5091 open ports**. For **363 hostnames**, which resolved out to **373 IP addresses**, finding **5091 open ports** yields a significant target list for further analysis. It's possible that some of these IPs are honeypots, but that still gives a nice target list for further analysis.

[Read full article](https://isc.sans.edu/forums/diary/Adding%20some%20Automation%20to%20the%20favicon.ico%20method%20of%20Host%20Recon/33110/)