---
layout: post
title: Javascript String Mehtods
author: Anthony Oglesby
date: 2020-07-03 09:07:51 -0400
---

# Javascript String Methods

Next up on the list of basic javascript stuff is string methods. These methods are used to manipulate string data. Strings values that contain a long sequence of characters that are usually surrounded by double quotes `""` or single quotes `''`.

## .length

the `.length` method is used when you want to know exactly how many characters are in a string.

so if we wanted to know how many character where in the variable x, if `const x = "Hello, world!";` we would use the `.length` method like so.

- in our console type

```bash
> const x = "Hello, world!";
undefined
> x.length
13
```

Remember that `.length` is counting every character in the string, that is everything within the double quotes. This includes the comma, the bang, and the space. So if we count this to verify we indeed get 13.

## .indexOf()

What if we want to know where in a string a specific word or character is?

Take for instance the alphabet.

`var alph = "abcdefghijklmnopqrstuvwxyz"`

If we wanted to know the position of `k` we would simply write `alph.indexOf("k")`. One thing to note is that indexOf starts counting at 0, so a's position would be zero.

Lets see this in the console.

```bash
> var alph = "abcdefghijklmnopqrstuvwxyz"
undefined
> alph.indexOf("k")
10
```

Another thing to note is that the indexOf method will only find the position of the first occurrence of the specified value. So if there were 3 more Ks in our alphabet this method would only find and return the position on the first K it finds and then it will stop. If we want to find the last occurrence we would use the similar `.lastIndexOf()` method.

And the last thing to note is that both of these methods accept a second parameter. This second parameter is the start point for which the method will begin it search. So `alph.indexOf("k", 5)` will begin is search for the letter K at position 5 of the string which would be the letter F. `alpha.lastIndexOf("k", 5)` does the same however it works backwards, so it will start the search for letter K at the fifth to last position of the string, which would be letter U.

# slice(), substring(), and substring

All three of theses methods return an extracted part of a string in very similar ways So we will go over just the slice method and talk a little bit about the other two after.

### slice()

The slice method takes two parameters. The first is the start position of the part of the string you want extracted. the second is the end position.

So lets take, `const str = "My dog is blue."` and just extract out "My dog"

```bash
> const str = "My dog is blue"
undefined
> str.slice(0, 6)
'My dog'
```

and if we just wanted the word blue

```bash
> const str = "My dog is blue"
undefined
> str.slice(10, 14)
'blue'
```

Pretty neat. Now a couple things to note.
- Slice will accept negative numbers as parameters.
- Slice will accept one parameter, if only one parameter is set it will slice the string from that start position and return everything after.
- The Substring method works exactly the same way however it will not accept negative values as parameters.
- The Substr method again works exactly how slice does, however substr's second parameter specifies the length of the part of the string you want extracted.
So if `str.slice(10, 14) = "blue"` then `str.substr(10, 4) = "blue"`

```bash
> str.slice(10, 14)
'blue'
> str.substr(10, 4)
'blue'
```

# Replace

The replace methods does what you propbably assume it does. It will replace a part of a string with a specified value.

So if `const str = "My dog is blue."` and we wanted to change "blue" to "red", we would simply

```bash
> const str = "My dog is blue"
undefined
> str.replace("blue", "red")
'My dog is red'
```

- Replace will only replace the first occurrence of the target value and it is case-sensitive. Be mindful of these rules when using the `replace()` method.
To work around these rules we can use the /g and /i flags. I wont go into much detail here but be sure to look them up.

# toUpperCase and toLowerCase

These to methods are super simple and very similar. They do exactly what they say they do. So lets just take a look.

```bash
> const str = "My dog is blue"
undefined
> str.toUpperCase()
'MY DOG IS BLUE'
> str.toLowerCase()
'my dog is blue'
```

# Concat

The `concat()` method takes two strings and joins them together. If we had two strings "Hello" and "World" we could use the + sign to type out the strings individually in order to join them together

```bash
> "Hello" + " " + "World"
'Hello World'
> const x = "Hello"
undefined
> const y = "World"
undefined
> x + " " + y
'Hello World'
```

This works, but its ugly. Instead we can use the concat method like so,

```bash
> const x = "Hello"
undefined
> const y = "World"
undefined
> x.concat(" ", y)
'Hello World'
```

That's better.

## Trim

The `trim()` method is used when we want to remove whitespace from a string. This is usfull when we are doing something like scrapping a website's data and a returned string is full of whitespace. Let's take a look.

```bash
> const str = "         Save me from space!               "
undefined
> str.trim()
'Save me from space!'
```


This was a good introduction to string operations. These methods will be some of the most common methods you use to work with strings, but further knowledge is always important so do more research!!
