---
layout: post
title: '[Mac][Rails]Install ROR on Mac OSX'
date: 2012-10-10 12:02
comments: true
categories: Rails, Mac

---
	
1.	Install RVM stable with ruby:<br> 
<pre>
$ curl -sSL https://get.rvm.io | bash -s stable --ruby
</pre> 

2.	Add rvm into $PATH<br>
<pre>
$ echo '[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm" ' >> ~/.profile
</pre> 
3.	Evaluate profile as a Tcl script<br>
<pre>
$ source ~/.profile
</pre> 
4.	Install RAILS <br> <pre>
$ sudo gem install rails
</pre> 
5.	Check rail’s version <br> <pre>
$ rails -v
</pre> 
