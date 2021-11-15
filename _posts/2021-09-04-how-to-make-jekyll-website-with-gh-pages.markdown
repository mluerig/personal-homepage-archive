---
layout: posts
title:  "How to make a static website with Jekyll and host it with GitHub (for free!)"
date:   2021-09-04 15:00 
categories: tech, how-to
---

*This is a series of posts where I document some of the techy things I do for my work as a scientist. My motivation for these posts is to both document the procedures for myself and help share them among the science community. My goal is to focus on writing more posts rather than making each post all-encompassing, but if I am missing relevant information please do let me know and I will add it.*

I like the concept of a personal website to feature scientific interests, resources, or other relevant information related to working as a scientist. What I don't like is spending a lot of time manging content or dealing with bloated and unflexible website management systems, like wordpress. With [github-pages](https://pages.github.com/){:target="_blank"} , a website and its content can be easily hosted and managed through a regular github repository. Together with [jekyll](https://jekyllrb.com/){:target="_blank"}, a generator for static websites that uses [markdown](https://www.markdownguide.org/getting-started/){:target="_blank"}, content management becomes incredibly simple. Here is a short introduction to get a website up and running in a few minutes. 

1. Install [Jekyll](https://jekyllrb.com/docs/installation/){:target="_blank"}: 
	- download and install Ruby (a high-level programming language) - simply follow the [instructions on the Ruby community website](https://www.ruby-lang.org/en/downloads/){:target="_blank"}
	- update gems, Ruby's package management system: `gem update`
	- GCC need to be installed and your system. On Windows, if you install Ruby through the ruby installer, GCC will become available through the MSYS2 devkit installed after the Ruby installation - simply hit "Enter" when you see this: 
	
	<div class="res-center">
	<div class="res-container">
	<img class="res-img" src="/assets/images/posts/msys2_win.png">
	<div class="res-caption">

	- Make needs to be installed on your system. On Windows, you can use chocolatey ([install first](https://chocolatey.org/install){:target="_blank"}): `choco install make`
	- test installations: `jekyll -v`, `ruby -v`, `make -v`
	
	
2. Fork a template 

3. Edit and preview locally on your machine

4. push 

5. keep up to date