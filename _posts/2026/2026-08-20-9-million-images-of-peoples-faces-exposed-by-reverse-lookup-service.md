---
title: 9 Million Images of People's Faces Exposed by Reverse Lookup Service
date: 2026-08-20
categories: [PRIVACY]
tags: [IMAGES,PRIVACY,SECURITY,DATA-BREACH]
---

## 9 Million Images Exposed! 🚨

Researcher Jeremiah Fowler discovered a cloud database containing over **9 million image files** accessible without authentication, as reported by WIRED. This leaky bucket, holding approximately **450 GB of images**, was traced back to a US-registered company called **ClarityCheck**. ClarityCheck claims: 
> "Use reverse image search to identify anyone in a photo. Find names, social profiles, and online presence in seconds."

While ClarityCheck asserts it does not utilize facial recognition, it describes its image function as a means to identify individuals and find their names and social profiles.

### Why This Matters ⚠️
It's crucial to remember that faces are persistent identifiers. Unlike a leaked password, which can be reset, a person cannot easily replace their face. When an image is linked with names, social profiles, addresses, emails, or phone numbers, that information could be misused for **impersonation**, **targeted phishing**, **doxxing**, or **catfishing**.

ClarityCheck disputed the claim that the data was publicly exposed, stating that accessing it required an unindexed URL. However, the images did not require authentication, and Fowler was able to discover the URLs through the site's code. It remains unclear how long the bucket was exposed before Fowler found it. Despite earlier alerts from Fowler, ClarityCheck did not restrict access to the database until WIRED contacted them in July.

### Important Tips for Users 📝
Here are a few pointers for those using ClarityCheck or similar tools:
- **Do not upload a photo of someone else** unless you have their permission or a clear legal right to do so.
- **Think twice** before uploading your own photo if you're unsure how it will be used, how long it will be stored, and how secure that storage is.
- Before using any service, check its policies on **image retention**, **deletion**, **AI model-training use**, **storage**, **third-party sharing**, and **removing images**.
- If you find yourself in a search result, save the URL and screenshots, request delisting from the search service, and seek removal from the original site or platform hosting the image.

For more details, [Read full article](https://www.malwarebytes.com/blog/privacy/2026/08/9-million-images-of-peoples-faces-exposed-by-reverse-lookup-service).