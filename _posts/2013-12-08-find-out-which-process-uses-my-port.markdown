---
layout: post
title: "Find out which process uses my port"
description: ""
date: 2013-01-20
category: Dev
tags: [node.js, system, macos]
comments: false
---

Today I had the problem, that someone has used the port 3000 on my macbook and I couldn't start my node.js server.
At first I tried to close all open terminal windows and exit the terminal app, but this wasn't the solution for my problem.

Now I've tried to find out wich process uses the port. For that I entered the following command in the terminal:

  lsof -i :3000

Now I got the process id of the process that is using the port. With the pid it's now very simple to kill the process with the following command.

  kill -9 11381
