---
layout: post
title: '[Mac]Delete Repeat Item in the Menu'
date: 2013-04-08 12:02
comments: true
categories: Mac

---

It’s annoyed since there are repeat items in the menu, and here is the solution to deal with this problem.

<pre><code>$/System/Library/Frameworks/CoreServices.framework/Frameworks/LaunchServices.framework/
Support/lsregister -kill -r -domain local -domain system -domain user
</pre></code>  
  
