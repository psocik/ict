---
title: XSSing TypeErrors in Safari
date: 2025-05-30
categories: [SECURITY]
tags: [XSS,TYPEERROR,SAFARI,SECURITY RESEARCH]
---

I was playing around with HackPad on Hackvertor when I remembered that Safari used to have an XSS issue in the actual TypeError. I’d used it before, but it caught my attention again because I’d recently been researching ways to conceal payloads in window.name and execute them using exception handling.

In case you’re not familiar, here’s what the traditional vector looks like:

> throw onerror=eval,name

Pretty cool - but it got me thinking: what if I could combine the TypeError XSS with the error handler somehow? That way, I could drop the need for the throw statement altogether and still trigger the exception handler.

To read the complete article see: [XSSing TypeErrors in Safari](https://thespanner.co.uk/xssing-typeerrors-in-safari).