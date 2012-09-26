---
layout: post
title: "Fix Wordpress MySQL Character Set"
description: ""
category: Tech Notes
tags: [Wordpress, MySQL]
---
{% include JB/setup %}

For MySQL database set up by old version of Wordpress, the charecter set was latin1. Altering the tables' collation etc won't affect the existing tables. One way to get it convert from latin1 to utf8 properly is by exporting and then importing:

	mysqldump -uUser -pPass --opt --quote-names --skip-set-charset --default-character-set=latin1 wp_database_old > wp_dump.sql
	mysql -uUser -pPass --default-character-set=utf8 wp_database_new < wp_dump.sql
	
Some other basic MySQL commands:

	##create a database
	CREATE DATABASE database_name;
	
	##add user
	GRANT usage on *.* to user@localhost identified by 'password';
	
	##grant privileges on database to user:
	GRANT all privileges on database_name.* to user@localhost;

	##switch to database:
	USE database_name;