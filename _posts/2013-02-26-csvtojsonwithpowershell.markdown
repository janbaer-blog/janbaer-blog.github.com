---
layout: post
title: "Csv to Json with Powershell"
date: 2013-02-26
categories: [csv, powershell, json]
---

In my current project I have got some .csf files with the requirement to import these files to my project as base data to use it as inmemory repository. A .csf file contains between 400 and 700 records.  My first thought was to create a small helper class with the ability to import these files and export them as json  to store them as resources in my project. After that, I would deserialize these with JSON.NET, a very fast library.   Before I invest one hour ore more to write my import and export classes, I've googled for existing solutions for this task. I founded some websites like [this](http://www.cparker15.com/code/utilities/csv-to-json/) with the ability to convert it online. But the best solution was these single line of code in powershell.

```
Get-Content -path $inputFile | ConvertFrom-Csv -Delimiter ';' | ConvertTo-Json | Out-File $outputFile
```

You can download the complete powershell script from my [gist repository](https://gist.github.com/janbaer/5045798) at github.
