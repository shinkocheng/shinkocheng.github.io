---
layout: post
title:  "X11 connection rejected because of wrong authentication after `sudo` to another user"
date:   2014-08-31 14:46:55 -0800
categories: workflow
---

This is a posting for my reference. I lifted this from [Jianming Li](https://jianmingli.com/wp/?p=724) in case one of these days he decides to take it down.

Cause: X win cookie not carried over after sudo login as another user.

Solution: Add the cookie to the other user.

From user1

{% highlight console %}
$ echo $DISPLAY
localhost:10.0

$ xauth list
box.my.com/unix:10  MIT-MAGIC-COOKIE-1  4f76c629f8cdbf26ce4ae646cc24448c
box.my.com/unix:11  MIT-MAGIC-COOKIE-1  1acd10ab0fd098a86aba7aa691d7c067
box.my.com/unix:12  MIT-MAGIC-COOKIE-1  e007ee6844c417a6b866d66c7bbcbc7d
{% endhighlight %}

From User2 (even root)


