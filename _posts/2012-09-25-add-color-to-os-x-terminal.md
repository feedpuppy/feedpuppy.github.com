---
published: true
layout: post
title: Add color to OS X terminal
description: ""
category: Tech Notes
tags: 
  - terminal
  - OS X
---


## Make ls etc colorful 

*Source: [color terminal bash on the Mac (iTerm included)](http://blog.imzaid.com/color-terminal-bash-on-the-mac-iterm-included "color terminal bash on the Mac (iTerm included)")*  
*Good reference: [OS X Lion Terminal Colours](http://noiseandheat.com/blog/2011/12/os-x-lion-terminal-colours/ "OS X Lion Terminal Colours")*

Open up `~/.bash_profile` and paste the following codes:

	#enables color in the terminal bash shell export
	CLICOLOR=1
	#sets up the color scheme for list export
	LSCOLORS=gxfxcxdxbxegedabagacad
	#sets up the prompt color (currently a green similar to linux terminal)
	export PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;36m\]\w\[\033[00m\]\$ '
	#enables color for iTerm
	export TERM=xterm-color
	#sets up proper alias commands when called
	alias ls='ls -G'
	alias ll='ls -hl'
	
The color designators used in the LSCOLORS varable are as follows: 
	
	a black
	b red
	c green
	d brown
	e blue
	f magenta
	g cyan
	h light grey
	A bold black, usually shows up as dark grey
	B bold red
	C bold green
	D bold brown, usually shows up as yellow
	E bold blue
	F bold magenta
	G bold cyan
	H bold light grey; looks like bright white
	x default foreground or background
	
The order of the attributes is as follows, and they are set in foreground-background pairs:  
	
	1. directory
	2. symbolic link
	3. socket
	4. pipe
	5. executable
	6. block special
	7. character special
	8. executable with setuid bit set
	9. executable with setgid bit set
	10. directory writable to others, with sticky bit
	11. directory writable to others, without sticky bit
	
To reload (either one): 

	source ~/.bash_profile
	. ~/.bash_profile
	
	
## Make nano colorful

*Source: [Compile latest version of nano with syntax highlighting](http://wimpyshell.net/2012/01/18/mac-osx-lion-compile-latest-version-of-nano-with-syntax-highlighting "Compile latest version of nano with syntax highlighting")*

Download the latest version (2.2.6) of nano from [here](http://www.nano-editor.org/download.php). Unzip the file, build and install. 

	tar -xvf nano*
	cd nano*
	./configure
	sudo make && make install
	
To use this new nano version by default, export `/usr/local/bin` path to your paths:

	export PATH=/usr/local/bin:$PATH
	nano -V
	
Open `~/.nanorc` and paste the following codes:

	## Nanorc files
	include "/usr/local/share/nano/nanorc.nanorc"
	
	## C/C++
	include "/usr/local/share/nano/c.nanorc"
	
	## Cascading Style Sheets
	include "/usr/local/share/nano/css.nanorc"
	
	## Debian files
	include "/usr/local/share/nano/debian.nanorc"
	
	## Gentoo files
	include "/usr/local/share/nano/gentoo.nanorc"
	
	## HTML
	include "/usr/local/share/nano/html.nanorc"
	
	## PHP
	include "/usr/local/share/nano/php.nanorc"
	
	## TCL
	include "/usr/local/share/nano/tcl.nanorc"
	
	## TeX
	include "/usr/local/share/nano/tex.nanorc"
	
	## Quoted emails (under e.g. mutt)
	include "/usr/local/share/nano/mutt.nanorc"
	
	## Patch files
	include "/usr/local/share/nano/patch.nanorc"
	
	## Manpages
	include "/usr/local/share/nano/man.nanorc"
	
	## Groff
	include "/usr/local/share/nano/groff.nanorc"
	
	## Perl
	include "/usr/local/share/nano/perl.nanorc"
	
	## Python
	include "/usr/local/share/nano/python.nanorc"
	
	## Ruby
	include "/usr/local/share/nano/ruby.nanorc"
	
	## Java
	include "/usr/local/share/nano/java.nanorc"
	
	## AWK
	include "/usr/local/share/nano/awk.nanorc"
	
	## Assembler
	include "/usr/local/share/nano/asm.nanorc"
	
	## Bourne shell scripts
	include "/usr/local/share/nano/sh.nanorc"
	
	## POV-Ray
	include "/usr/local/share/nano/pov.nanorc"
	
	## XML-type files
	include "/usr/local/share/nano/xml.nanorc"
