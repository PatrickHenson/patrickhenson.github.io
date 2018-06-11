---
layout: post
title: "Getting Started with Uncrustify"
tags: [linux, c++]
---

Maintaining the _style_ of your code is manageable if it's just you, but how do you handle commits from an entire team? If you haven't used a code beautifier, such as [Uncrustify](uncrustify.sourceforge.net), they're extremely useful tools that keep your codebase consistently formatted.

Several benefits are immediately apparent:

* configurable to match your coding standards

* easily enforce and apply to your project(s) 

* prevent useless whitespace commits, fix alignment and indentation, place brackets inline or on a newline, etc

* allow code reviews to focus on features and architecture


### Install

Uncrustify is available on several Linux flavors and can be run in Cygwin on Windows.  I'm currently using an Ubuntu development environment at home.

```
sudo apt-get install uncrustify
```

### Configure

It's easiest to start with a pre-existing config file and edit to fit your coding standards.  You can find several examples online, Uncrustify provides a default config file [here](https://github.com/uncrustify/uncrustify/blob/master/documentation/htdocs/default.cfg)

### Run

Running uncrustify is pretty straight forward.  Check the --help for a full list of options.

```
# -c            point to where your config file is stored
# --no-backup   replace files without backups, prevents unnecessary files in your repo
uncrustify -c ~/uncrustify.cfg --no-backup *.cpp
uncrustify -c ~/uncrustify.cfg --no-backup *.h
```

However, that's not ideal.  I want to use a single command to run uncrustify recursively over all source files in my project.  Creating a custom alias will allow me to do this using a meaningful command ('uncrustify-all', 'formatcode', 'wtf-did-you-do-to-my-repo', etc).

This can be done by adding the following line to your .bashrc

```
alias uncrustify-all='find . \( -name "*.cpp" -o -name "*.c" -o -name "*.h" \) -exec uncrustify -c ~/uncrustify.cfg --no-backup {} +'

```

Now it's a simple matter to navigate to my project's directory, format, commit, and push.
