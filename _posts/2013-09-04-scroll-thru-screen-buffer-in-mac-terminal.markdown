---
layout: post
title:  "Scroll through screen buffer in MacOS Terminal"
date:   2013-09-04 14:46:55 -0800
categories: workflow 
---

I use screen a lot for work. but when i want to see the history in terminal,
typing `^a-[` and then up/down arrow gets tedious in a heartbeat. i discovered
recently that you can put the following command in the `~/.screenrc` file in the
machine where screen is run, and you’ll have the capability to scroll through
the history.

{% highlight bash %}
# Make xterm scrolling work properly with screen
termcapinfo xterm-256color|xterm-color|xterm|xterms|xs|rxvt ti@:te@
{% endhighlight %}

