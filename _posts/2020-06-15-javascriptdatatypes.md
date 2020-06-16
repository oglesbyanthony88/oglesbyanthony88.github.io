---
layout: post
title: Javascript Data Types
author: Anthony Oglesby
date: 2020-06-15 11:07:51 -0400
---

# Javascript Data Types Guide

**Intro**

This is going to be the first of a blog series in which I write little guides to explain programming concepts. I'll do my best to capture these concepts and explain them in an easy to understand way.

**Data Types**

First, let's answer the question, "What is a Data Type?".

A Data Type is a classification of data. (i.e. numbers, strings, true/false, etc) In order for a programming language to work properly we need to declare a data type so that it can interract with values properly.

For example our human brains would see 1 + 1 = 2 right? But a computer brain is a little bit more complicated. Why? because without telling the computer that the 1s are numbers it might assume that both are strings, (A collection of characters to form a human readable text.) so it might interprut that as "1 + 1" = "1 + 1" or "1" + "1" = "11". This will all become a little clearer when we talk about the different data types in general, but now that we get the basic premise lets move on.

**Strings**

Like I stated earlier a String is a collection of characters that form a human readable text. Strings are declared by surrounding the text with 'single' or "double" quotes.

Lets test this out. If you open a browser and turn on inspect, then go to console, we can try out some strings.

In the console type out `let string = "1 potatoe, 2 potatoe";`. When you hit enter the console will return undefined. DON'T WORRY! This is normal. All we did here was declare the variable `string` and give it a value of `"1 potatoe, 2 potatoe"`. Now go ahead and type `string` in the console and it should return `"1 potatoe, 2 potatoe"`.

By surrounding our text with "Double" quotes we let the computer know that the value of string is a string. This also works with 'single' quotes. We can also check to make sure that the variable `string` is a string by typing in the console `typeof string`. It should return `"string"`.

There are numerous fun things you can do with strings, so dont be afraid to look further into the string data type.

**Numbers**

Numbers are a pretty basic concept. We know 1 + 1 = 2, and so does the computer. Numbers are mainly used for maths, counting, and ordering things. There is no special way to declare numbers, so let's just play around in the console.

In the console type `1 + 1`. It should output `2`. we can do a bunch of different math operations with numbers. Type `200 / 4` and it should return `50`. This is because `/` is the math symbol for division in javascript. If we want to do multiplication we use the `*` symbol. so if we type `200 * 4` we should get `800` as the return value.

But what happens if we try to put a number in quotes? Well if we type `"2" + 2` we get `"22"` as a return. Why? Because we told the computer that one of the 2s is a string and not a number it doesn't do math. Instead it is going to concatenate. Meaning it is going to combine the string 2 and the number 2 and output the string 22. This is because we can not do math to strings. Imagine trying to divide "1 potatoe, 2 potatoe" by 2. Actually lets try it.

In the console type out `"1 potatoe, 2 potatoe" / 2` and hit enter. We get `NaN` as a return. This is a new return is what is returned when you try and do math with none number data types in javascript. NaN literally translates to Not a Number.

One Data type that is considered a number but has its own name is **Infinity**. This is returned when dividing by 0 or when the calculated number is too big.

If we type `200 / 0` the return will be `Infinity`

**Boolean**

Booleans are values associated with a true false value. These are used when we want to know if a statement or value is true or false.

Let's play around with this in console. Go ahead and type `let x = 5` and hit enter. Now type `x == 5`. You will see that `true` is returned. Let's break this down.

We created a variable `x` and gave it a value of `5`. We then used what is called a *Comparison Operator* to check if the value of `x` was equal to the value of `5`. If we instead type `x == 6` it will return `false`.

**Array**

An array might be a little intimidating at first, but they aren't as bad as they seem. An array is a collection of datatypes stored in one variable. Array's are declared by wrapping its values in `[]` brackets, and can have multiple values inside of them.

Let's play with one in the console. Type `let array = [1,2,3,4,5]` and hit enter. If we type `array` it will return `(5) [1,2,3,4,5]`. `(5)` is the value equal to the number of values stored in the array, while `[1,2,3,4,5]` is the array itself. One thing to note is that all computers start counting at 0. So in order to find a specific value within an array we need to keep this in mind. What do you think happens when we try to find the second value in an array? How would we do this? Let's try it out. Type `array[2]` and hit enter. Remember we were looking for the second number in the array we created. However when we entered the above code it returned the third number in the array, according to our human brains. remember computers start counting at 0. so we need to remember that [1,2,3,4,5] is positioned as [0,1,2,3,4]. Let's try to find the second value in our array again. Type `array[1]` and it will return `2`.

Another fun thing we can do is store strings in an array. Let's try this out.

In the console type `let sentence = ["Hello", "world"]` and hit enter. Now type `sentence.join(" ")` and it will return a string `"Hello world"`. There are endless possibilities for arrays. After you are comfortable with the basic data types, mastering arrays is essential.

**Objects**

Objects are a bit more complicated than arrays. While and array can store multiple values, an object can store multiple arrays.

For example an object could look something like:

```javascript
let Owner = {
  "name": "Steve",
  "pets": ["Terrance", "Wendle", "Fang"],
  "pet_type": ["dog", "cat", "fish"],
  "pet_age": [5, 3, 1]
};
```

This isn't as scray as it seems. All this means is that Steve has 3 pets named Terrance, Wendle, and Fang. Terrance is a dog that is 5 years old, Wendle is a cat that is 3 years old, and Fang is a fish that is 1 year old.

Go ahead and copy the above code and paste it into your console.

Now, let's see, how can we find the Owners name. Simple! in the console type `Owner.name`. It will return `Steve`. What about the name of his first pet? Type `Owner.pets[0]` and it will return `"Terrance"`. And if we want to know how old Terrance is we just type `Owner.pet_age[0]`.

Objects can become much more complicated that the one above but learning them is key to being successful as a coder. play with this one or create your own. There are lots of great resources to get a more advanced understanding of all of the data types above.
