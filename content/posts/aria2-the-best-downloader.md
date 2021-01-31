---
title: "Aria2 : The Best Cross Platform Download Utility"
date: 2021-01-31T10:37:58+05:30
tags:
    - linux
    - cli-tools
series:
    - linux-tools
---

If you have been looking for a minimal command line download utility for Linux, look no further than **[aria2](https://aria2.github.io/)**

According the the official website.

> aria2 is a lightweight multi-protocol & multi-source command-line download utility. It supports HTTP/HTTPS, FTP, SFTP, BitTorrent and Metalink. aria2 can be manipulated via built-in JSON-RPC and XML-RPC interfaces.

## Features

-   Downloads any file from internet
-   Supports Multipart Downloads like [IDM](https://internetdownloadmanager.com)
-   Downloads torrents
-   Minimal, Lightweight and [Open-Source](https://github.com/aria2/aria2)

## Installation

**On [Arch](https://archlinux.org) / Arch Based distros:**

```bash
pacman -S aria2
```

**On [Ubuntu](https://ubuntu.com) / Debian based distros:**

```bash
apt install aria2
```

## Usage

**To download any file over internet by splitting in 8 parts and downloading them simultaneously:**

```bash
aria2c -s 8 -x 8 <link>
```

Note: `-x 8 -s 8` splits file into 8 parts and downloads them simultaneously, you can use `-s 16 -x 16` for 16 parts.

Example:

```bash
aria2c -s 8 -x 8 https://github.com/aria2/aria2/releases/download/release-1.35.0/aria2-1.35.0.tar.gz
```

**To Download a torrent**

```bash
aria2c <magnet link>
```

Example:

```bash
aria2c "magnet:?xt=urn:btih:5fff0e1c8ac414860310bcc1cb76ac28e960efbe&dn=ubuntu-20.10-desktop-amd64.iso"
```

Or with a `.torrent` file

```bash
aria2c path/to/torrent_file
```

Example:

```bash
aria2c ubuntu-20.10-desktop-amd64.iso
```
