---
title: "The hugo new command and how to make it useful for you"
date: 2021-02-28T13:35:27-06:00
description:
draft: false
hideToc: false
enableToc: true
enableTocContent: false
tocFolding: false
tocPosition: inner
tocLevels: ["h2", "h3", "h4"]
tags:
- hugo
series:
-
categories:
- hugo
- blogging
- quick tip
image:
---


Hugo includes a `hugo new` command, which will create a new file for you
using one of your [archetypes](https://gohugo.io/content-management/archetypes/) as the initial content. 

You can make this even more useful by setting hugo to automatically open your editor after using this command.

<!--more-->

## Via Environment Variable

This would be my preferred option in a repository where multiple users
collaborate on content, as it's likely they will prefer a different editor
than I do.

You can set the `HUGO_NEWCONTENTEDITOR` environment variable to your editor
of choice as follows:

```bash
export HUGO_NEWCONTENTEDITOR="/usr/bin/vim"
```

Once you've done that, simply `hugo new post/newpost.md` and you'll be
greeted with your editor of choice, simple as that!

## Via Command Line Arguments

You can also specify an editor with `--editor=/usr/bin/vim` on the command
line, for instance `hugo new --editor=/usr/bin/vim post/newpost.md`

This is useful if you've already got an editor set up, but want to use a
different one for some reason.

## Via config.toml 

And finally, if you're the only one working in this repository, the best way
is probably to set the option in config.toml:

```toml
NewContentEditor = "/usr/bin/vim"
```

