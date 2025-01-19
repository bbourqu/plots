---
title: Keeping Firefox from trying to search my local domain
pubDate: 01/19/2025 13:10
upDate: 01/19/2025 13:10
author: "Brett"
tags:
  - Firefox
  - Search
  - Custom
  - Domain
imgUrl: '../../assets/firefox-pug.png'
description: Keeping Firefox from trying to search my local domain
---


# Keeping Firefox from trying to search my local domain

For all my services that are local I tried out the [.local domain](https://en.wikipedia.org/wiki/.local) but for
whatever reason my network doesn't like to resolve them.  So now I use the `.pug` domain for all my services that I
expose through [metallb](https://metallb.io/) and [pihole]() using dns and cname resolution.  The issue that I ran 
across is that in firefox, it always tries to search with my default search provider unless I add `http://`.  This 
is annoying on my phone and even in my browser window.  To fix this I added a `boolean` value under the
following key: `browser.fixup.domainsuffixwhitelist.pug` 

## References

[https://support.mozilla.org/en-US/questions/1292986](https://support.mozilla.org/en-US/questions/1292986)