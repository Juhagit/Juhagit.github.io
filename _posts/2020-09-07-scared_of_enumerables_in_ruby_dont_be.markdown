---
layout: post
title:      "Scared of Enumerables in Ruby? Don't be!"
date:       2020-09-07 08:10:08 +0000
permalink:  scared_of_enumerables_in_ruby_dont_be
---



First thing you might find asking yourself is that what even is an Enumerable? Sure, Ruby's Enumerable module is named with a great lack of imagination, but don't let that fool you! It let's you to take your Ruby skills to new heights!



Enumerables are a collection of iteration methods. Iterate means doing one thing multiple times and that is exactly what Enumerables do, traverse through objects. That might sound a bit weird or in some way even confusing, but we'll go over each method with a simple example which allows you to get the idea behind it! In this quick guide to Ruby's Enumerables I'll discuss of .map, .find, .each and .select.

#### .map

Also called as .collect. Map returns an array (no exceptions!) with same number of elements as the array you called it on. It returns modified array and the original array stays unmodified. Enumerable methods work by giving them a block in which you tell Ruby what you'd like to do to your array.
How it looks in practice? Let's take a look!


> [1,2,3].map {|x| x + 1}
> #=> [2, 3, 4]


In this simple example .map went through each element of the array and returned an array with same number of elements incremented by one. The element which is contained within the pipes( || ) is like a placeholder. Whatever you put there represents each each element of the array in turn and performs given task to them.
Not so scary huh?

####  .find

This method has an alias as well called .detect which does exactly the same task as .find. Purpose of this method is to fetch an element for you and when it finds the first element which is not false .find returns it to you. Here's an example of said method:

array_1 = [1,2,3,4,5,6,7]
array_1.find{|x| x > 5}

#=> 6

Here we created an array called array_1 and used .find method to find the first value which is greater than 5 which in this case is 6. If none of the elements wouldn't have matched the criteria it would have returned 'nil'.
As mentioned before .find stops running when it finds first element which holds true and returns the said element.

#### .each

Each is Ruby's way of doing "repeat until it's done". It loops over the array and performs a given task to each element one by one. Let's demonstrate it with an example!

[1,2,3].each {|n| puts "Current number is #{n}" }
Current number is 1
Current number is 2
Current number is 3

Here we have an array that contains numbers 1,2 and 3. Placeholder "n" between the blocks and in a string represents each element of the array in question. Here Ruby replaces the placeholder with each element one by one and we end up with 3 sentences!

#### .select

Select stands behind it's name; it selects elements for us! Unlike find it returns us all elements that are true.

array_1 = [1,2,3,4,5,6]
array_1.select {|n| n > 3 }
#=> [4, 5, 6]

Great! Just what we wanted. Wonder what happened to our array_1, did we modify it? Let's find out.
array_1
#=> [1, 2, 3, 4, 5, 6]

Our array stays the same so it's a non-destructive method. Method called .reject is complete opposite of .select.
array_1.reject {|n| n < 4}
=> [4, 5, 6]

If we want to get rid of our first three elements in our array we can do that just as easy as well!
array_1.delete_if {|n| n < 4 }
array_1
#=> [4, 5, 6]

There's tons of different Enumerables in the Rubyland, but worry not, there's no need to hardcode all of those in your mind! You can find more information about those here: https://ruby-doc.org/core-2.7.1/Enumerable.html


Practice makes perfect and that's the case here as well! So now that you've learned about some of the Enumerable methods it's your turn to open up your editor and put these methods in practice! :)
