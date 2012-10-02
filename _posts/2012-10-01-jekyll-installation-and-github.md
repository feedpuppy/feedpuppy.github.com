---
layout: post
title: "Jekyll Installation and Github"
description: ""
category: Tech Notes
tags: [Jekyll, Github, Git, Linux]
---

## homebrew
Before installing [Homebrew](http://mxcl.github.com/homebrew/), first need to install Xcode and Xcode command line tools. Then run the following commands to install homebrew:
	
	> /usr/bin/ruby -e "$(/usr/bin/curl -fsSL https://raw.github.com/mxcl/homebrew/master/Library/Contributions/install_homebrew.rb)" 
	
## rbenv, ruby
Install the ruby version management tool [rbenv](https://github.com/sstephenson/rbenv
	
	> brew update
	> brew install rbenv

Add rbenv init to your shell:

	> echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
	
Install ruby-build which simplifies the process of installing new versions of Ruby

	> brew install ruby-build
	> rbenv install 1.9.3-p194
	
Rebuild the shim binaries. Need to do this any time a new Ruby binary is installed

	> rbenv rehash
	
Set global version of Ruby (default one from OSX is called System)

	> rbenv global 1.9.3-p194
	
Other commands:

	## list all Ruby versions known to rbenv
	> rbenv versions
	
	## display current active Ruby version
	> rbenv version
	
	## set per-project local Ruby version
	> rbenv local 1.9.3-p194

## Jekyll and Github
Install Jekyll gem

	> sudo gem update --system
	> sudo gem install jekyll
	
Create a new repository **username.github.com** in Github, and clone jekyll-bootstrap project and set remote url etc. 

	> git clone https://github.com/plusjade/jekyll-bootstrap.git USERNAME.github.com
	> cd USERNAME.github.com
	> git remote set-url origin git@github.com:USERNAME/USERNAME.github.com.git
	> git push origin master
	
Build the site and set local jekyll server, and the site is available at http://localhost:4000

	> jekyll --server 4000

Other basic Jekyll and Git commands:

	## create post, and page
	> rake post title="Post Title"
	> rake page name="Page.md"
	
	## commit and publish. -a is to skip staging
	> git add .
	> git commit -am "commit comment"
	> git push
	
	## pull new version from remote
	> git pull
	
	
------------	
_References:_

* _[搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html "搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门")_ 
* _[Relaunching my Blog on Jekyll](http://anupjadhav.com/2012/04/22/relaunching-my-blog-on-jekyll/ "Relaunching my Blog on Jekyll")_
* _[Jekyll Bootstrap](http://jekyllbootstrap.com "Jekyll Bootstrap")_
* _[Pro Git Book](http://git-scm.com/book "Pro Git")_