---
layout: post
title:      "Cattlelog Sinatra App Prep"
date:       2019-10-09 23:10:46 -0400
permalink:  my_sinatra_app
---


My first app is under way!  For my second portfolio project, I am building an app for my dad.

This app is called "Cattle-Log".  The catalog for your herd.

My notes below were crucial in my development.  Writing out the structure allowed for a reference when building out the MVC.  Next, the migrations!

What are we keeping track of ?
	- cows
		age, weight, type, color, health
	- farm
		acreage, crop, coordinates, image?
	- expenses
		notes, feed, fertilizer, miscillaneous, price
		
**notes for sinatra project**

Show page for User
> outside gems for support on build
> corneal gem for migrations
> current market price (formula -- maybe nokogiri) https://beefmarketcentral.com/ nokogiri gem
> pictures of the farm -- https://stackoverflow.com/questions/8956249/image-scraping-in-ruby
> exepnse uploader -- https://www.engineyard.com/blog/a-gentle-introduction-to-carrierwave
> weather
> date, time

Models
	user
		username
		password
	cows
		age
		type
			cow 
			steer
			bull
		weight
		color
		field_id
	fields
		acreage
		coordinates
	expenses
		cost
		picture
		notes

Views
	cattle
		index all instances
		new form
		edit form
		show one #id redirect is cattle/show = show page to render

	fields
		index all
		new forms 
		edit forms
		show one
		
	expenses
		index all
		new forms 
		edit forms
		show one

	user
		index all
		new forms
		edit forms
		show one

Controllers

CRUD

	cows
		index
		show
		edit
		delete
	
	fields
		index
		new
		edit
		show
	
	users
		new
		create/signup
		show of profile
		
	expenses
	  index
		new
		edit
		show

DB
	create users-->create table users
		users
		email
		login/ password
		
	create cattle-->create table cows
		type
		age
		weight
		color
		health
		
	create farm-->create table fields
		field
		acreage
		
	create expenses-->create table expenses
	  image
		notes

- validate email/password - authentication bcrpyt - has a secure password (completed)
- cattle model validate *cannot enter blank information into the data

Specific side notes for cattle_id
	route --> to the page --> /cattle/1 --> particular id information
	post updates --> redirect back to different route --> this will be the specific isntance or 	intepolate








