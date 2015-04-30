---
layout: post
title: "Hashception: Part I"
date: 2015-04-29 17:59:36 -0400
comments: true
categories: "hashes inception dicaprio dreams"
---
A lot of programming is working through layers of data to retrieve or manipulate the necessary values. Wading into giant, deep containers of virtual lists an associatons can be daunting, but once you get more familiar with them, they come easier to navigate.

We’ve invited the characters of the movie Inception to help us out.

![inception poster: hanging around in the middle of a street that curves 90 degrees vertically](http://topwalls.net/wp-content/uploads/2012/04/inception-movie.jpg)

Let’s say you’re a contractor hired by the Tap Soft Drink company to infiltrate potential customers’ dreams and place bottles of Tap in “meaningful” parts of their dreams. They also want you to collect data on the content of people’s dreams, so that they can market to the public better. You’re a bit rusty on your dream infiltration technique, so you ask the team from Inception to bring you up to speed. 

The dream layout looks something like this:

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

The first thing is that you want is to get in and out of the dream as quickly as possible while completing your objective. Without the right constrainsts, you can end up stuck in a dream, forever!

Don’t do this: 

  ```ruby
    while dream do
       print “#{dream[:items]} ,”
    end

Or this:

    loop do
       print “#{dream[:items]} ,”
    end

  ```

You will end up with this:

![infinite loop unresponsive message](http://matthew.komputerwiz.net/wp-content/uploads/2015/01/chrome-infinite-loop.png)

![limbo and total desctruction](http://media.giphy.com/media/ZAv0VrzFL29k4/giphy.gif)

You've entered a never-ending loop that crashes your program!
 
You need to supply the variables to make sure you have a safe time. An incrementor like i is handy. The flow i =0, i < (a number) and i+=1 inside the loop can help keep everything in check.

Even better are methods that run through each element of data structures like an Array (similar to a list of elements) or a Hash (a list of keys that each point to, or associate with, a value). These types of methods, like each, collect, select and inject use an object called a block while operating. You can think of the block as an ambiguous dreamlike space that methods can yield their consciousness to. Just like dreams, things outside the block can appear inside the block, but anything defined in the block don’t exist on the outside.

Let’s go through a few main methods that you might use:

####Each 

The .each method goes through each element, hands it over to the block, and returns exactly what you gave it. It’s like having a dream, forgetting about it, and going about your day the next morning. One of the ways programmers use .each is by printing out each element from the block to the screen.

Array: 

  ```ruby
      [1, 2, 3, 4].each do |num|             
           num * 2                                      
        end
  =>     [1, 2, 3, 4]

  ```

Hash: 

  ```ruby
    names = {:name_one => “Julian”, :name_two => “Jeremy”}
    names.each do |key, value|
      value + “is awesome”             
    end
    =>   {:name_one => “Julian”, :name_two => “Jeremy”}

  ```

####Collect

The .collect method is the “inception” method. Whatever happens inside the block changes the data structure .collect is affecting. You can plant easter eggs in the array or hash, and manipulate things to your liking. Dom Cobb would be proud.

![Leonardo explains: And we bring the subject into that dream](http://media.giphy.com/media/qLuZhQmSOvcAM/giphy.gif) 

![Leonardo explains: And they fill it with their subconscious](http://media.giphy.com/media/S5S8rQ50V0ITK/giphy.gif)

Array: 

  ```ruby
      [1, 2, 3, 4].collect do |num|             
           num * 2                                      
        end
  =>     [2, 4, 6, 8]

  ```

Hash: 

  ```ruby
    names = {:name_one => “Julian”, :name_two => “Jeremy”}
    names.collect do |key, value|
      value + “is awesome”             
    end
    =>   {:name_one => “Julian is awesome”, :name_two => “Jeremy is awesome”}

  ```

####Select

The .select method returns a data structure filled only with values that are inherently true. How you define what is true inside the block is up to you. This method is great for filtering out unnecessary parts of an array or dream, and obtain only the element you wanted all along.

Array: 
  
  ```ruby
      fruits = ['apple', 'banana', 'apple', 'banana']
      fruits.select do |num|             
           'apple'                                      
        end
  =>     ['apple', 'apple']

  ```

####Inject

The .inject method takes an element and makes it interact with the upcoming elment. It keeps carrying over these values until they accumulate until it accumulates into a giant final snowball. It's like bringing on what you come across in one dream on to the next dream.

Array: 

  ```ruby
      [1, 2, 3, 4].inject do |sum, num|             
           sum + num                                      
        end
  =>     10  

  ```                     
    
Now that we have the tools to do basic iteration, next post we'll tackle the dream.

 


