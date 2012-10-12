---
layout: post
title: "Remote Host Identification Has Changed Error"
description: ""
category: Tech Notes
tags: [ssh]
---
For "Remote Host Identification Has Changed" error, you can just deelt the file:

	rm .ssh/known_hosts
	
Or probably better, only remove relevant keys:

	> ssh-keygen -R {server.name.com}
	> ssh-keygen -R {server.ip.address}
