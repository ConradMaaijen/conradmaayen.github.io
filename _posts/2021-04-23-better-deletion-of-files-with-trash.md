---
layout: post
title: "Better deletion of files & folders with Trash"
categories: original
author: "Conrad Maaijen"
---

Ever got to the point when you did a `rm delete-me.txt` and then realized you made a mistake in deleting this file.
Luckily we have a Trash bin right? Well we have, but the `delete-me.txt` file is not in it. Sure, `rm` completely removes the file from your computer.

<!--more-->

Better would be installing `Trash` on your machine. Trash moves you file to the Recycle bin like it does when you remove a file using the Finder on a Mac. So let install [Trash](https://github.com/sindresorhus/trash).

```bash
$ npm install --global trash-cli
```

Now you can use the `trash` command in you terminal.

```bash
$ trash delete-me.txt
```

Or move a complete folder to the Recycle bin:

```bash
$ trash foldername
```

I'm sure you feel a lot more secure now when you are deleting files or folders from your machine using the terminal.
