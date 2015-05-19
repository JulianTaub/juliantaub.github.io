---
layout: post
title: "Tooling and Tasks: Configuring the Odds in Your Favor"
date: 2015-05-18 19:08:20 -0400
comments: true
categories: "Flatiron&nbsp;School rake tasks gunt ruby rails" 
---
Nothing gives you the edge more than creating your own toolbox to problem solve faster and more effienciently. As developers, we want to go in, keyboards blazing. But going through the motions of setting things up can easily get in your way.

Building up a treasure trove of smart tasks and shortcuts abstracts away a lot dirty work, so that you can focus on the bigger picture. You can set up tasks to automate all facets of your interaction with a program: the front end, back end, and even the keyboard. Here are some shortcuts I've been exploring:

##Back End: 

##Rake Tasks

Rake tasks are part and parcel of the rails framework, but you can easily set up your own custom ones. 

You can create tasks that load different environments, install themes, generate templates, seed data, organize folders, and clean up unwanted files. 

All the tasks will be stored in a RakeFile, where you can handpick what gems and dependencies are required. 

Rake uses an intuitive and abstracted language to explain your tasks clearly. For example, a task making a new postmay look like: 

```ruby
desc "Makes new blog post"
task :generate_post do
  # makes a new post by targeting a directory and adding a new file with predetermined markup. 
    .....
  end
```
Or to preview a simulation

```ruby
desc "Starts simulation"
task :simulate do
  # loads environment, starts server and runs scripts 
    .....
  end
```

###Gems

Extending your built in functionality is important in creating an awesome and robust program that feels intuitive. 

Gems are stored in the Gemfile, which is created during the bundle install command in the Terminal. Their dependencies and versions are safeguarded by the Gemfile.lock file. 

Some cool and useful gems I've come across:  

[Logstash](https://github.com/elastic/logstash)  
[RubyCritic](https://github.com/whitesmith/rubycritic)  
[Faker](https://github.com/stympy/faker)  
And lots more gems on the [Ruby Gems](http://rubygems.org) website.

##Front End

###Gruntfile.js

Grunt runs tasks with javascript using Node.js. It can run asynchronous tasks, check for typos in syntax, uglify files, and generate JSON. There are also tons of [plugins](http://gruntjs.com/plugins) available for Grunt. Here are some good tutorials on how to start installing a using it:  

[Grunt: Getting Started](http://gruntjs.com/getting-started)  
[Grnt.js: The Basics](https://quickleft.com/blog/grunt-js-the-basics/)  

##Text Editors

Both [Sublime Text](http://www.sublimetext.com/) and [Atom](https://atom.io/) have awesome autocompletion and snippets, however Sublime gets annoying quickly with popups to purchase their product, while atom is free.

To the more hardcore programmers, the solution is either Vim or Emacs. Vim has a lot of shortcuts and starts with them as default, and emacs allows you to customize commands across many platforms. You can learn about both in the links below:  

[Interactive Vim Tutorial](http://www.openvim.com/)  
[Absolute Beginner's Guide to Emacs](http://www.jesshamrick.com/2012/09/10/absolute-beginners-guide-to-emacs/)   











