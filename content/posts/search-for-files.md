---
date: '2025-05-21T09:34:47+10:00'
title: 'Search for Rare Quake Files'
---

I'm doing a first-pass search for files for the [Quake3 Official Archive](/blog/posts/quake3-official-archive/).

I have [notes on finding rare files here](https://gist.github.com/Jason2Brownlee/9c6c219b82463631f727fc903cc3a4c4) but I'm being super systematic for this first pass and thought I should document it (for next time).

First, the given is we know what we are searching for, e.g. we have a wishlist of known filenames.

The first pass involves either finding the file or collecting all known locations where the file used to exist. Later we can dig further into each URL via the wayback machine to learn more.

1. Find all historical locations for the file on the [Quake Archive Search](https://github.com/Jason2Brownlee/QuakeArchiveSearch). My private DB of URLs has 50M+ entries at this point.
	1. Check each URL in the wayback machine, if downloaded, stop.
	2. Add all file URLs to the wishlist URLs file.
2. Search on the Internet Archive (it's not well indexed)
	1. [Discmaster](https://discmaster.textfiles.com/) (possibly find)
	2. [Archive](https://archive.org/) (possibly find)
3. Search on [GoogleGroups](https://groups.google.com/) (historical URLS)
	1. Add all new URLs for the file to the wishlist URLs.
4. FTP Search (possibly find, or get historical URLS)
	1. [Mamont](https://www.mmnt.ru/) (historical URLs)
	2. [Napalm](https://www.searchftps.net/) (possibly find)
5. Web Search (possibly find, historical URLs)
	1. [Google](https://www.google.com/)
	2. [Yandex](https://yandex.com/)
	4 [Duckduckgo](https://duckduckgo.com/)