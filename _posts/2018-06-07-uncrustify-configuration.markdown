---
layout: post
title: "Get Started with Uncrustify"
tags: [linux, c++]
---

If you haven't used [Uncrustify](uncrustify.sourceforge.net) before, it's an extremely easy way to ensure that your codebase is consistently formatted.

Maintaining the _style_ of your code is manageable if it's just you, but how do you handle commits from an entire team?  Enter _code beautifiers_ such as Uncrustify.  It uses a configurable recipe to ensure that whitespaces, alignment, braces, etc follow an agreed upon format.  This helps prevent useless 'whitespace commits' and allows your code reviews to focus on more important issues.  If you don't want to use Uncrustify, there are many other code beautifiers available through the command line or as add-ons to your favorite editor.

First, install uncrustify.  I'm using an Ubuntu based development environment, but you can install it on other Linux flavors or run it in Cygwin on Windows.

```
sudo apt-get install uncrustify
```

Then configure the _recipe_ you want to use to format your code.  It's easiest to start with a pre-existing config file and edit to fit your coding standards.  The default uncrustify config file can be found [here](https://github.com/uncrustify/uncrustify/blob/master/documentation/htdocs/default.cfg)

Running uncrustify is pretty straight forward.

```
# -c            point to where your config file is stored
# --no-backup   replace files without backups, prevents unnecessary files in your repo
uncrustify -c ~/uncrustify.cfg --no-backup *.cpp
uncrustify -c ~/uncrustify.cfg --no-backup *.h
```

However, that's not ideal.  I want to use a single command to run uncrustify recursively over all source files in my project.  Creating a custom alias will allow me to choose a meaningful command ('uncrustify-all', 'formatcode', 'wtf-did-you-do-to-my-repo', etc) to do this for me.

```

```

I chose to go with 'uncrustify-all'.  Now it's a simple matter to navigate to the top directory of my project, uncrustify my changes, commit, and push.
