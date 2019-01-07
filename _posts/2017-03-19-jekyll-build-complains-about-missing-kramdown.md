---
layout: post
title: Jekyll build complains about missing "kramdown"
date: 2017-03-19 22:23
categories: 
tags: [jekyll, ruby, Uncategorized]
---

When running **jekyll build** for a Jekyll site without any plug-in, Jekyll might complain about kramdown is missing:

    Dependency Error: Yikes! It looks like you don't have kramdown or one of its dependencies installed. In order to use Jekyll as currently configured, you'll need to install this gem. The full error message from Ruby is: 'cannot load such file -- kramdown' If you run into trouble, you can find helpful resources at https://jekyllrb.com/help/!
  
The solution is to add Jekyll in Gemfile:
```
source 'https://rubygems.org'
gem 'jekyll'
```
