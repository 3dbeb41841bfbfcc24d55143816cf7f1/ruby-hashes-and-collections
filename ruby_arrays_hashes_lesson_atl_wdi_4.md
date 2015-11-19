# Arrays, Hashes, & Blocks

### Objectives

- Use basic array methods including count, first, and last
- Iterate through arrays with map and each
- Use the appropriate data collection for a situation: hash vs. an object 
- Get and set values for specific hash key
- Get a list of all keys in a hash

### Preparation

- Recall the differences between use-cases and definitions for arrays & hashes 
- Name the equivalent of a hash in JS
- Iterate on, get information out of, and put information into arrays & JS objects

## Intro (5 mins)

Because you'll be using arrays & hashes so, so much in your time as a developer, we want to get you up to speed with how to work with them.

For these Ruby data collections, you'll be reminded of similar ideas in JS. That's fantastic. Anytime you can draw on that connection to help yourself guess at what methods might exist, or even just what to Google, you'll be in good shape.

DISCUSSION: What are some real scenarios that can be mapped as arrays?

## Working with Arrays - Demo (20 mins)

Just as a refresher – what are arrays for? What do they do? **They're for holding a collection of values**, that's it.

#### Making Arrays, Adding to Arrays

So, let's start simple – we make arrays in Ruby the same as we did in JS. Nothing unexpected here.

```ruby
numbers = [1,2,3,4]   # I'm obviously an array

numbers = []          # To create an empty array  
numbers = Array.new   # Not as common  
```

Then, once you've created an array, how do you imagine you add to an array?

```ruby
numbers.push 5 # dun, dah nun dun dun dun, push it
# => [1,2,3,4,5]
```

Similarly, we've got another old favorite – the shovel.

```ruby
numbers << "six" # there no shovel puns to see here
# => [1,2,3,4,5,"six"]
```

#### Removing From Arrays

Now, obviously it's possible to mix data types (Ruby does not care), but why would we want to? That'll be weird. Let's get rid of one.

```ruby
numbers.delete "six" # give it the value you want to get rid of
# => [1,2,3,4,5]
```

#### Useful Array Miscellany

There are so many great array methods - here are a few you'll probably use from time to time.

```ruby
# how many values are there?
numbers.length # => 5, of course

# just as you'd expect, get's the value at nth index
# remember, and indexes start at 0!
numbers[3] # => 4

# a handy method equivalent to numbers[0]
numbers.first
# also a handy method equivalent to numbers[numbers.length-1]
numbers.last

# and what if we need to rearrange? so useful!
numbers = [3,2,4,1,5]
numbers.sort # [1,2,3,4,5]
numbers.sort.reverse # => [5, 4, 3, 2, 1]
```

#### Useful Array Miscellany - Part II

Let's create an array of colors.

```ruby
# this will create an array of objects
colors = %w(orange yellow blue)

# to find the index of green
colors.index("yellow")

# assignment
colors[1] = "green"
colors[10] = "pink" # note that Ruby will add 'nil' placeholders

# modifying
colors.pop                          # pops the last one off the array
colors.unshift("red")               # adds at index 0
new_colors_array = colors.shift(2)  # grabs the quantity of objects starting with index 0 and creates a new_colors array
colors.delete('green')              # delete objects

```

**YOU DO** 

Create a to-do list at least 5 tasks long (e.g.- **`to_dos = [“dishes”, …]`) -- start with “dishes” and include “walk the dog” somewhere. Using Ruby, answer:

- First thing you need to do (should be “dishes”)
- Last thing you need to do
- What index is “walk dog”?
- Write commands to update the list by following along with this story:
	- You did the last thing on the list
	- You just did the dishes
	- You just remembered you want to do something right now
	- You just remembered you want to do something when all the other stuff is done



## You're Ready to Move On to Hashes

####Distinguishing when to use arrays and/or hashes
We use hashes constantly. Hashes, like JS objects, are a great way to store related data of all different kinds, in a way that's super readable. They're also referred to as **associative arrays**.

**WE DO** - Tell me what to name this variable 

```
[“milk”, “eggs”, “beer”, “bread”]
```

Tell me what to name this variable:

```
[“brown”, 2, “blue”, “Alabama”]
```

Let's rearrange previous array of self into hash that’s clear. Arrays are best for lists and hashes are best for explaining an object.

```
marc = {
	hair: "brown",
	eyes: 2,
	eye_color: "blue",
	home_state: "Alabama"
}
```

The key to hashes is that they always house key/value pairs. **The key describes the properties, the value is the information relating to or describing the property.**


**YOU DO** - Hashes - Independent Practice

Now you try it!

- Partner up! Together and by hand with markers on the desk, describe something using an array -- feel free to make it challenging. Use any data types you can think of, cuz hash values can be anything!
- When you're done, each of you, independently open your computer, write it out in IRB. Try getting each key out, adding in new ones, and deleting ones just for fun.
- In your hashes, try to:
	- Include one key value with the value as an array
	- Include one key value with the value as another hash (look to the fan hash from earlier!)
	- Remember, use the "new way" of creating hashes, if you remember how!

#### Creating a Hash

To see it in action, let's pick something random in the room and try to describe it.

> **Note:** just to prove hashes can hold all kinds of great data, let's see how many different data types we can describe our object with!

For example, let's describe a fan in the room.

```ruby
fan = {
  type: 'freestanding',
  blades: 5,
  speeds: ['low', 'medium', 'high'],
  rotating: false,
  height: {
    measurement: 100.4,
    unit: 'cm'
  }
}

# additional ways to create a hash
hash = {}
hash = Hash.new 
```

Nice! Good work.

Now, based on what you know about how JS objects work, how would you guess we grab data out of here? 

```ruby
# Let's say we want to know how many blades it has...
fan[:blades]       # => 5

# Or check the keys or values...
fan.keys
fan.values

# Or if we want to confirm if our object posesses a particular key...
fan.has_key?[:speeds]
```

**YOU DO -** Create a hash that describes this WDI class:

- One of the values should be a number (ex: number of students)
- One should be a boolean
- One should be an array
- One should be a string



#### Symbols Are For Memory

> _"Hold up, what's the colon? In JavaScript, we'd use ``fan['blades']``, why does that not work?"_ - Roughly half the classroom, in their brains

Well, young padawans, that's because our keys up above are symbols, not strings.

Symbols are basically just like strings, except they save computer memory.  Every string you create is unique and takes up space on your computer, even if they're the same value! When we're busy looking up key/value pairs, we don't want to be wasting memory - we want it to be fast!

Let's watch:

```ruby
"Your Name".object_id
#=> a number

"Your Name".object_id
#=> a different number

:your_name.object_id
#=> a number

:your_name.object_id
#=> the same number!
```

Symbols on their own don't do much, but they work great as keys. There are two ways to write them:

```
{
  # from older ruby versions, still totally work
  :the_old_way => 'some value',

  # from newer ruby versions, which is just shorter
  the_new_way: 'some value'
}
```

Either are fine; you'll see both a lot. Use the "new way" one if you can help it, just cuz it's nice.

For the record, strings as keys _are_ possible – we just try not to use them.

#### Adding to our hash

Real quick – what if we forgot a key/value pair, or want to add one in after the fact?

```ruby
fan[:color] = 'silver'

fan = {
   type: 'freestanding',
   blades: 5,
   speeds: ['low', 'medium', 'high'],
   rotating: false,
   height: {
     measurement: 100.4,
     unit: 'cm'
   },
   color: 'silver'
 }


# Or if we want to update the number of blades it has...
fan[:blades] = 6   # => 6
```

#### Guess how to get rid of a key/value pair?

Given we just learned to do this with arrays, it's okay to be unsurprised.

```ruby
fan.delete :color
# remember, parentheses are optional!
```

#### Accessing nested collections
Let's take a look at some nested collections.

```ruby
# multi-dimensional arrays
colors = [[‘blue’, ‘yellow’, ‘red’], [‘green’, ‘orange’, ‘purple’]]

colors[0][1] == “yellow” # => true

# arrays in hashes
class = { attitude: “awesome”, instructors: [‘Mike’, ‘Marc’, ‘Bruce’] }

original_instructor = class[:instructors].last


# hashes in arrays
marc = { nickname: ‘Marcus Aurelius’, mastery: ‘long stories’ }
bruce = { nickname: ‘Club Lyfe’, mastery: ‘debugging’ }
mike = { nickname: ‘Magic Mike’, mastery: ‘Pretty much everything, it’s actually quite impressive’ }

instructors = [marc, bruce, mike]
bruce_nickname = instructors[1][:nickname]
mikes_mastery = instructors.last[:mastery]

```

Soon we’ll be able to write `instructors.last.nickname` -- different syntax, much easier to read and write

**Closing**

- How do we distinguish between when to use arrays vs hashes?
- What if we want to do something with each one in an array? (Like print each item?) Do we know how to do that? We’ll learn that next lesson.


## Hashes - Independent Practice (10 minutes)
Now you try it!

- Partner up! Together and **by hand with markers on the desk**, describe your computer as a hash. Use any data types you can think of, cuz hash values can be anything!
- When you're done, each of you, independently **open your computer, write it out in IRB**. Try getting each key out, adding in new ones, and deleting ones just for fun.
- In your hashes, try to:
  - Include one key value with the value as an array 
  - Include one key value with the value as another hash (look to the fan hash from earlier!)
- Remember, use the "new way" of creating hashes, if you remember how!

## Conclusion (5 mins)

- How do you get the 4th item of an array?
- How do you get a value out of a hash?
- How do you add a value to a hash? What about an array?
