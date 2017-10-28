---
layout: post
title: '[Homebrew][Mac]Use Homebrew to Replace Macports'
date: 2012-10-10 12:02
comments: true
categories: Rails, Mac

---
	
<h2>Part I:</h2>

<h4>RemoveMacPorts:</h4>
<pre>
$ sudo port -f uninstall installed
</pre>
<pre>
$ sudo rm -rf \
/opt/local \
/Applications/DarwinPorts \
/Applications/MacPorts \
/Library/LaunchDaemons/org.macports.* \
/Library/Receipts/DarwinPorts*.pkg \
/Library/Receipts/MacPorts*.pkg \
/Library/StartupItems/DarwinPortsStartup \
/Library/Tcl/darwinports1.0 \
/Library/Tcl/macports1.0 \
~/.macports
</pre>

<font color=red>No sudo:</font>
<pre>
$ sudo chown -R `whoami` /usr/local
</pre>

Install Homebrew:
<pre>
$ ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
</pre>

<h2>Part II:</h2>
<h4>Using Homebrew to install software:</h4>
<pre>
$ brew search wget
</pre>
<pre>
$ brew install wget
</pre>

<h4>Other Homebrew commands:</h4>
<pre>
$ brew list   — list installed software
</pre>
<pre>
$ brew update   — Update Homebrew
</pre>
<pre>
$ brew -h  — Help 
</pre>

<h4>Remove Homebrew:</h4>
<pre>
$ cd `brew --prefix`
</pre>
<pre>
$ rm -rf Cellar
</pre>
<pre>
$ brew prune
</pre>
<pre>
$ rm -rf Library .git .gitignore bin/brew README.md share/man/man1/brew
</pre>
<pre>
$ rm -rf ~/Library/Caches/Homebrew
</pre>
