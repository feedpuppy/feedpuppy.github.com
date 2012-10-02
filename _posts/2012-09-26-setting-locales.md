---
layout: post
title: "Setting Locales Errors"
description: ""
category: Tech Notes
tags: [Linux]
---

The error message says:

	perl: warning: Setting locale failed.
	perl: warning: Please check that your locale settings: 
    
To fix the error, install locales. 

	apt-get install locales
    
Then run the following command, use space bar to select needed locales

	dpkg-reconfigure locales

Also useful

	locale-gen