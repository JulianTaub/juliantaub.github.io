---
layout: post
title: "Where the Value Goes"
date: 2015-04-29 17:45:36 -0400
comments: true
categories: "values programming variables return"
---
One crucial topic I constantly come across as I am studying at Flatiron is that I always need to be aware and keep track of what values my variables hold throughout my code and how they change over time.

I cannot drill this into my head enough. Or tell you how many times being sloppy has ruined an afternoon.

Let’s start at the very beginning…

The Ruby language has very few set keywords, so most of the work will come from you, the programmer, defining your own variables, meaning storing information by associating a name with a value (or technically, an object that has a value):

 ```ruby
  x = 14
  food = “pasta”
  cities = [New York, Berlin, Dallas, Shanghai]
  ````

You use the variables as placeholders for data, so you can manipulate it for whatever program you’re working on. The problem arises when you call methods on the data, functions that operate on data in specific ways. Some are fairly straight forward. For example, most people can infer that: 

  ```ruby
  x = 14
  x = x + 6
  ```` 

reassigns x to equal 20. However, other methods are less obvious. It’s always important to understand how each one “returns” a value. A method like puts prints to your screen, but returns a nil value. Other methods will change a copy of the data, leaving the variable’s original data intact.

  ```ruby
  puts “Return me, please!” # => nil

  name = “Julian”
  name.upcase  # => “JULIAN”
  name         # => “Julian” 
  ````

Some guidelines to keep in mind while tracking your variable:

  -  Ruby always returns the last value of a program. Think of how to use that to your advantadge.
  -  Ruby has built-in implicit returns, meaning just writing the variable is enough to get the value.
  -  Just because something is printed on the screen, doesn’t mean that the same value was returned in the program.
  -  Keep track of incrementing values, and methods that take multiple arguments
  -  Always read documentation for the nitty-gritty details. [Ruby-doc.org](http://ruby-doc.org/) is the place to be.
  -  Get dirty in the sandbox: Test out code snippets in the terminal using *irb*, or hacking into programs as they are running, using the *pry* gem.


