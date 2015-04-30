---
layout: post
title: "Hashception: Part II"
date: 2015-04-29 18:09:05 -0400
comments: true
categories: 
---
In the last post, we gathered up some useful methods for our journey. Now let’s take next step: entering the dream space. 

Remember that this is our target dream:

  ```ruby
    dreams = { 
     :dream_one =>{
        :location => "grandma's house",
        :people => ["Grandma", "Grandpa", "Sis", "Brother", "Auntie Charlotte"],
        :discussions => ["ancient aliens", "superheroes turned Senators", "ninjas"],
        :items => {
          "bratwurst" => {
             :color => 'Firetruck red',
             :shape => 'Cylindrical',
             :satisfying => true,
           },
          "sofa" => {
             :color => 'burnt sienna',
             :shape => 'L-shaped',
             :satisfying => true,
           }
        }
      }
     :dream_two =>{
        :location => 'enchanted forest',
        :people => ['woodsman', 'wizard', 'Sleepy Tom', 'Butters', 'Tinkerbell'],  
        :discussions => ['politics', 'magic','good', 'evil'],
        :items => {
           "tree of life" => {
               :power => 'vivaciousness',
               :state => 'glowing',
               :color => 'golden',
               :shape => 'branchy',
               :blissful => true   
               },
            "magic potion" => {
              :power => 'strength',
               :state => 'bubbly',
               :color => 'purple',
               :shape => 'liquid',
               :blissful => false   
              } 
         }
     }     
    }

   ``` 

Still scary, right? Not to worry - as we venture through the levels of the dream, we’ll keep track of where we are at in two ways:
drawing out our current level in a comment above a method
a handy library (referred to as ‘gems’ in Ruby) called ‘pry’

Adding comments (descriptive lines that don’t affect your program) above your code can help you map out the dream as you work your way through it and be used as a reference points if you get stuck.

Pry, on the other hand, freezes a program as it’s running and lets you peer inside of it. 

![Freeze frame of girl throwing orange up in the air and reflection in mirror walking away](http://media.giphy.com/media/cxged4or0Ksmc/giphy.gif)

It even lets you play around with all the inner variables and test them all out.  All you need is two lines of code inserted into the area that you want to check out:

  ```ruby
  require ‘pry’
  binding.pry
  ```

‘Require’ imports the gem into your file, so it can be on hand, and the second line triggers pry to stop whatever program that crosses paths with it and reveal its binding. Binding is the ‘universe according to that line of the program’ - all of its variables, methods, and values.

###Entering the Dream

As you enter the dream, you have two goals in mind:

  -  Collect data on the dream
  -  Add bottles of Tap to the dream

Let's start with the top level:

  ```ruby
  # Level 1: Tale of Two Dreams
  # dreams = {:dream_one => {...}, :dream_two => {...}}
  dreams.each do |dream, dream_content|


  end
  ```

We're just scoping out our path interating through the dream, so we haven't added anything logic inside the block yet. Also, make sure that you name your parameters (here 'dream' for the keys and 'dream content' for the values) in a way that is clear and makes sense to you.

This level doesn't seem that useful. We're ping-ponging between two dreams, each pointing to nested hashes which contain the dream content. So...

!['We need to go deeper' meme from inception](http://i2.kym-cdn.com/photos/images/facebook/000/531/557/a88.jpg)

Let's enter the next level:

 ```ruby
  # Level 1: Tale of Two Dreams
  # dreams = {:dream_one => {...}, :dream_two => {...}}
  dreams.each do |dream, dream_content|
    # Level 2: Content is King
    # {:location => "...", :people => [...], :discussions= [...], :items => {...}}
    dream_content.each do |type, attributes|


    end
  end
  ```

Here we have much more to work with. We have a list of different types of data in the dream (location, people, and items), a map of where different things may be located, and an overall sense of the string's structure.

The marketing company wants to know each type of content, and the structure that each one points to. They also want to compare this level between different dreams.

Easy enough. Lets iterate through everything and print it to the screen, focusing on the type name and the attribute Object class:

 ```ruby
  # Level 1: Tale of Two Dreams
  # dreams = {:dream_one => {...}, :dream_two => {...}}
  dreams.each do |dream, dream_content|
    # Level 2: Content is King
    # {:location => "...", :people => [...], :discussions= [...], :items => {...}}
    dream_content.each do |type, attributes|
     puts "#{type} points to a(n) #{attribute.class}."
    end
  end

  => location points to a(n) String.
     people point(s) to a(n) Array.
     discussions point(s) to a(n) Array.
     items point(s) to a(n) Hash.
  ```

  Now that you have printed out this information, you have everything you need to incept bottles of Tap into the dream. You know where you want to insert them and the data structures you'll be dealing with. Therefore, you can prepare the path to inception and methods needed beforehand.

  Let's get two new bottles of Tap for dream insertion:

  ```ruby
    tap_one = Tap.new
    tap_two = Tap.new
  ```  

We're going to target the discussion and item types. Discussion points to an array, meaning that we can just push tap_one into the end of the array. Let's also use .collect to iterate over dream_content, so that the inception will be sure to solidify:

```ruby
  # Level 1: Tale of Two Dreams
  # dreams = {:dream_one => {...}, :dream_two => {...}}
  dreams.collect do |dream, dream_content|
    # Level 2: Content is King
    # {:location => "...", :people => [...], :discussions => [...], :items => {...}}
    dream_content[:discussions].push(tap_one)
  end
```

Next, we want to pass tap_two into items. We don't know what items themselves point to inside the hash, but we don't need to. Brands love distinguishing themselves from the flock, so we just have to make whatever tap_two points to compelling. Here we go:

```ruby
  # Level 1: Tale of Two Dreams
  # dreams = {:dream_one => {...}, :dream_two => {...}}
  dreams.collect do |dream, dream_content|
    # Level 2: Content is King
    # {:location => "...", :people => [...], :discussions => [...], :items => {...}}
    dream_content[:items][tap_two] = "Amazing thirst-quenching childhood nostalgia popularity comfort love belonging individuality"
  end
``` 

You successfully incepted this dream! The marketeers are overjoyed. The campaign was a success and you're getting job offers left and right for inception contracts, even from the US government- regarding a secret mission to incept the dreams of foreign revolutionaries and make them more America-friendly.



