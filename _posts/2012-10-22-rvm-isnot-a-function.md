---
layout: post
title: '[RVM] RVM Is Not a Function, Selecting Rubies With Rvm Use … Will Not Work'
date: 2012-10-22 12:02
comments: true
categories: Rails, RVM

---

Reference:<br>
http://stackoverflow.com/questions/9336596/rvm-installation-not-working-rvm-is-not-a-function <br>
https://rvm.io/support/faq#shell_login <br>
https://rvm.io/integration/gnome-terminal	<br>

<img src="/images/rvmerror.png">
<br>
Sometimes it happens suddenly, and it&rsquo;s really annoyed!</p>

<p>Let&rsquo;s check this deeply, and see what&rsquo;s going on here!</p>

<p>I provide two parts, solution and the reason.</p>

<h3>PartI: Solution.</h3>

<ol>
<li><p>Turn off your terms, and make sure you&rsquo;ve done this carefully.</p></li>
<li><p>Open a single new term.</p></li>
<li><p>Type &lsquo;/bin/bash &ndash;login&rsquo;.<br></p></li>



<pre><code>$ /bin/bash --login
</code></pre>



<li>Check if it works.<br></li>
</ol>

<ol>
<pre><code>$ type rvm | head -n 1
</code></pre>

</ol>
<p><br>
You&rsquo;ll see &ldquo;<font color=red>rvm is a function</font>&rdquo;, if it worked.</p>

<p><img src="/images/rvmerrorsolution.png"></p>

<h3>PartII. Summary.</h3>

<p>Because you are not using a login shell.</p>

<p>When the terminal is on, it will be a &lsquo;non-login shell&rsquo;, and it&rsquo;ll only load &lsquo;.profile&rsquo;(or .bashrc).</p>

<p>This will cause that .bash_login will be ignored, and rvm will be ignored.</p>

<p>It happens when you open multiple terms sometimes.</p>
</div>
  
  
