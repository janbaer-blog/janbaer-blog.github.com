---
layout: post
title: "Find out which process uses my port"
description: ""
date: 2013-12-08
category: develop
tags: [node.js, system, macos]
comments: false
---

Today I had the problem, that someone has used the port 3000 on my macbook and I couldn't start my node.js server.
At first I tried to close all open terminal windows and exit the terminal app, but this wasn't the solution for my problem.

Now I've tried to find out wich process uses the port. For that I entered the following command in the terminal:

{% highlight bash %}
lsof -i :3000
{% endhighlight %}

This command returns me informations about the process that is using my port. With the processid I'm now be able to kill the process.

{% highlight bash %}
kill -9 11381
{% endhighlight %}
