---
layout: post
title: "About PATH in Mac OS X"
description: ""
category: Tech Notes
tags: [PATH, OS X]
---
First, to find out your current PATH:

	echo $PATH$
	
Add a directory to the variable for current bash session:

	export PATH=path_to_be_added:$PATH

You can set values in `~/.bash_profile` so it will work for all future bash sessions. Also the order of directories matters. For example, if you put `/usr/local/bin/` before `/usr/bin/`, then software installed in the former directory would override those in the latter one. 

For Mac OS X, there are two other places:

* `/etc/paths` contains all default directories that are added to PATH.
* files under `/etc/paths.d` are added to PATH as well. 

If you don't want to change the order of the directories, you can set an alias in `~/.bash_profile` to tell the system which executable to run

	alias nano="/usr/local/bin/nano"
	
----------
_References:_

* <http://superuser.com/questions/284342/what-are-path-and-other-environment-variables-and-how-can-i-set-or-use-them>
* <http://superuser.com/questions/20934/conflicts-between-usr-bin-and-usr-local-bin>