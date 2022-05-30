# Understanding The Problem Domain Is The Hardest Part Of Programming

What is the hardest thing about writing code? There are many common answers to this question: 

- Learning new technology
- Naming things
- Testing your code
- Debugging
- Fixing bugs 
- Making software maintainable

## A Familiar Problem

By creating a familiar problem domain, you're making it so trivial that it is easily understood, you are able to make learning easier. 

## Why Are Problem Domains So Hard? 

Ever tried solving a puzzle like this one? 

[World's Most Difficult Jigsaw Puzzle](puzzle.jpg)

The reason why puzzles like this one are so hard, is because you can't really see what you are trying to build very clearly. Normally when you put together a jigsaw puzzle you follow steps that might look something like this: 

1. Figure out what the major components of the picture are
2. Sort the pieces by colour or component 
3. put together all the border pieces
4. Put together each component of the picture from piles you created 

This breaks down when you don't have a picture with clear components that you can identify. **The same thing happens when writing code.**

Writing code is a lot like putting together a jigsaw puzzle. We put together code with the purpose of building components that we have taken out of the 'bigger picture' of the problem domain. The big issue is that many problem domains are like puzzle with a blurry picture or no picture at all. 

**The real world is a messy place. Many of the problem domains we face as programmers are difficult to understand and look completely different depending on your point of view.**

## Promgramming is easy if you understand the problem domain

It is very difficult to solve a problem before you know the question. It's like buzzing in on Jeopardy before you hear the clue and shouting out random questions. 

If understanding the problem is the hardest part of programming and you want to make it easier, you can do one of two things. 

1. Make the problem domain easier
2. Get better and understanding the problem domain

**You can often make the problem domain easier by cutting out cases and narrowing your focus to a particular part of the problem.**

What I mean by this is that it is often beneficial to take a part of the problem and fully understand that part before expanding the problem domain.

Games are really good at this.  Look at most games today and you’ll find that you start with a very small problem domain.  The first level is usually a tutorial that has a basic set of things you can do so that you don’t get overwhelmed.  But, as you advance through the levels, you usually find they get harder and introduce new concepts that build gradually on what you know, until you understand a pretty large problem domain.

The other choice is to become better at understanding problem domains.  As developers, we tend to think that sitting down and talking to customers or business people who know about the problem domain is a waste of time. It is easy to fall into the trap of thinking you understand enough of the problem to get started coding it.  Best to resist the temptation to “not waste anymore time talking” and make sure you understand a problem inside and out before you try and solve it with code.  It is much more expensive and time consuming to do things over than it is to do them right the first time.  I learn this lesson the hard way time and time again.

# What's the difference between primitive values and object references in JavaScript?
## A critical distinction between immutable and mutable data

All data types (string, number, boolean) in JavaScript can be put into one of two categories: **primitive values** and **object references.**

**Primitive values** and **object references** behave differently. This difference in behavior affects how variable assignments are made, how equality operators get their results, and *how JavaScript programs run in general*.

Understanding the difference between **primitive values** and **object references** is critical to mastering JavaScript as a programming language. This piece will explain and illustrate this distinction in depth.

The following details will be covered:

- What JavaScript data types fall into each category.
- The difference between a value and a reference.
- The difference between immutable and mutable data.
- Practical examples comparing how primitive values and object references work.
- Classifying JavaScript’s Eight Data Types

JavaScript currently supports eight different data types. This includes seven primitive value types and objects. Here’s the full list.

- **Boolean**
- **Null**
- **Undefined**
- **Number**
- **BigInt**
- **String**
- **Symbol**
- **Objects**

If you are new to JavaScript this list may look strange to you: arrays, functions, and dates are all missing.

This isn’t a mistake. Arrays, functions, and dates all play an important role in JavaScript programs, but they are really just **objects under the hood.**

## The Difference Between a Value and a Reference

**Primitive values** and **object references** are stored in JavaScript programs in different ways.

When a **primitive value** is assigned to a variable (eg let cat = ‘Bear’), the variable is set to that value directly.

When the variable is assigned with an **object**, however, things are different. Instead of containing the value directly, that variable contains a reference to it. Here’s an example:

```
const moe = {
  name: 'Moe Szyslak',
  occupation: 'Bartender',
  voicedBy: 'Hank Azaria'
}
```

When the code above is executed, JavaScript creates the object and stores it somewhere in computer memory. The variable moe does not contain the new object directly, it contains a reference to the memory address that currently stores the object.

This is a bit like how a street address does not contain all the information associated with a particular residence, it just contains where the residence is located geographically.

## The Difference Between Immutable and Mutable Data

One key difference between **primitive values** and **object references** is mutability. **Primitive values** are *immutable* and **object references** are *mutable.*

Put simply, this means that **primitive values** cannot be changed (or mutated), but **object references can be changed.**

To illustrate, let’s look at some code.

An example of immutable data

First, let’s look at an immutable data type — strings. To begin we will create a variable, word, and assign a value to it.

let word = 'snow'

The variable now exists in memory and you can access individual letters of the string by using square bracket notation. If I wanted to get the first letter, for example, I could check for the value in the 0 index and log it to the console.

console.log(word[0]) // "s"
Reading individual characters of the string is no problem. What you can’t do, however, is change (or write) these individual characters. Let’s see what happens when you try:

word[0] = 'k'
console.log(word) // "snow" (The code above did not change the word)
You can’t change the string because it is immutable.

If you need to get around this constraint you have to create a new string from the old one and reassign the word variable with that new value: word = `k${word.slice(1)}`console.log(word) // "know"

An example of mutable data

Next, let’s look at a mutable data type, arrays. Again — arrays are really just special objects in JavaScript.

let letters = ['s', 'n', 'o', 'w']
letters[0] = 'k'
console.log(letters) // (4) ["k", "n", "o", "w"]
Since arrays are mutable you can alter them directly. There’s no need to assign a new value to letters since you can just change the existing array directly.

Aside: the code written above used the let keyword to create the letters variable, **but you could define the variable with const and the result would still be the same. const prevents you from reassigning values, but it does not prevent you from mutating existing values.**

How Primitive Values and Object References affect Variable Assignments
So far we’ve learned that variables set to Primitive Values contain actual values, and variables set to Object References just contain references (or memory addresses).

Let’s look at another explore how this fact affects how variable assignments. Here’s another example:

let lead = 'John Lennon'
let coLead = lead
coLead = 'Paul McCartney'
console.log(lead, coLead) // John Lennon Paul McCartney
The example above creates a variable named lead, then creates a new variable named coLead and sets it to contain the contents of lead. Then, on the third line, the value of coLead is reassigned (remember, strings are immutable so they can’t actually be changed).

Logging these variables shows that the values of lead and coLead are 'John Lennon' and 'Paul McCartney'.

Notice that although we assigned lead to coLead on the second line, the two values remained different after coLead was reassigned on the third line.

Now, let’s change the example slightly to use object references instead of primitive values:

let lead = {
  name: 'John Lennon',
  group: 'The Beatles'
}
let coLead = lead
coLead.name = 'Paul McCartney'
console.log(lead, coLead)
// {name: "Paul McCartney", group: "The Beatles"} is logged twice
The code above is very similar to the previous example. As before, the script creates a variable named lead, then creates a new variable named coLead and sets it to contain the contents of lead.

The key difference is on the line that changes the name property to ‘Paul McCartney’. Instead of reassigning the value of coLead, we mutate its existing object.

When we log the value of lead and coLead to the console, we see that they are now the same (apparently Paul McCartney is both the lead and co-lead.) What happened?

First, an object with a name property of ‘John Lennon’ was created somewhere in computer memory
The variable lead was given a reference, or memory address, to that newly created object.
On the second line, a new variable named coLead was created, and it was given the contents of lead. But remember that lead is not set to a direct value — it is just a reference. So coLead now contains a second reference to that same object that was created on the first line.
On the third line coLead is mutated. Since lead and coLead are referencing the same object, both variables appear to be changed.
This kind of thing is often a problem in JavaScript programs.

If you want to create a new object instead of a second reference to the same object (as we did above), you should use Object.assign instead:

let lead = {
  name: 'John Lennon',
  group: 'The Beatles'
}
let coLead = Object.assign({}, lead, {
  name: 'Paul McCartney'
})
console.log(lead, coLead)
// {name: "John Lennon", group: "The Beatles"}
// {name: "Paul McCartney", group: "The Beatles"}
The first argument that Object.assign accepts is the target object. Any arguments provided after this are source objects that will have their properties copied onto that target.

In the example above a new object ({})is created as the target (first argument), and then each property from the lead object is applied to it (second argument), and then a new name property (‘Paul McCartney’) is applied as well (third argument).

This approach allows you to copy one object from another and still keep the original object unchanged.

How Primitive Values and Object References affect Equality Comparisons
JavaScript programs often use equality operators to check if two values are the same.

Loose equality is checked using the == operator and strict equality is checked by using the === operator.

The loose equality operator (==) will return true if the values of the two items being compared are the same. The strict equality operator (===) returns true if the values and types of the two objects being compared are the same.

It is generally recommended that === be used over == whenever possible to avoid behavior that might not be expected (things like 0 == ‘’, for example). This tutorial will use strict equality exclusively, but the concepts discussed apply to loose equality as well.

Since primitives contain direct values, equality comparisons made with them perform in the way you probably expect:

'Moe Szyslak' === 'Moe Szyslak' // true
false === false // true
1970 === 1970 // true
undefined === undefined // true
Object references, on the other hand, do not contain values directly — they contain references. This causes equality checks with objects to give results that may not be intuitive to new developers:

{ name: 'Moe Szyslak' } === { name: 'Moe Szyslak' } // false
[] === [] // false
new Date(0) === new Date(0) // false
NaN === NaN // false (NaN is another type of object)
In all four of the object comparison checks above, a new object is created on both the left and the right of the === operator. Even though the contents of the left side are the same as the contents on the right side, the reference, or memory address that the contents are stored at, is different. This is why the comparison is found to be false in each case.

If you create a duplicate reference to the same object, you will see that the equality check is now found to be true:

let lead = {
  name: 'John Lennon',
  group: 'The Beatles'
}
let coLead = lead
console.log(lead === coLead) // true
In order to check whether the contents (not the reference) of two objects are the same you need to either:

Iterate through the object and check that each key and value match. This can be tricky because an object’s property can be an object in itself.
Convert the object to a suitable primitive before doing the equality check.
Here’s an example of how object literals can be converted to strings for comparison. This should be thought of as a quick-and-dirty approach, but I often find it handy.

const moeA = { name: 'Moe Szyslak' }
const moeB = { name: 'Moe Szyslak' }
moeA === moeB // false
JSON.stringify(moeA) === JSON.stringify(moeB) // true
And here is how dates, for example, could be converted to numbers for comparison:

const dateA = new Date(0)
const dateB = new Date(0)
dateA === dateB // false
dateA.getTime() === dateB.getTime() // true
Summary
JavaScript currently supports eight data types. All of these data types (Booleans, Null, Undefined, Number, BigInt, String, Symbol) are primitive values except for object references.

Many common data types such as arrays, functions, and dates are object references under the hood.

Primitive values can be stored in variables directly. Objects, on the other hand, are stored as references. A variable that has been assigned an object does not store that object directly, it stores the memory address of the location that the object exists at.

Primitive values are immutable — they cannot be changed after being created. Object references, however, are mutable and can be changed.

Since objects are stored as references, special care must be taken when duplicating objects and when performing equality checks on objects.

Understanding how these operations work can be confusing for newcomers to JavaScript, but they make sense once you understand how the language’s type system works.

Developing a strong grasp of primitive values, object references, and mutability is a critical step in progressing past the beginner stages of JavaScript programming.

This knowledge will help you identify bugs, understand key differences in programming paradigms, and help you understand your code at a deeper level.


