---
layout: post
title: Basic Bitwise Operations
author: Anthony Oglesby
date: 2020-06-15 11:07:51 -0400
---

# Basic Bitwise Operations

The first time I heard the term (Which literally was a week ago) basic bitwise operations, I was at a loss. I could have given anyone a hail mary guess as to what it was. I figure if I, a recent software engineering grad had no idea what basic bitwise was, then maybe im not the only one. So lets get into it.

In order to break down this concept we are going to take a step back into some very basic Computer Science concepts.

Lesson 1 - A computer does not speak in terms of numbers `1,2,3,4`, strings `"Hello, World!"`, or characters of any sorts `@#%*&aeiouAEIOU1234`. These characters are defined by bits, or binary digits. 1s and 0s. All data is stored in binary on a computer. In order for the computer to display these characters to the user it translates these binary patterns and displays them for us. Thanks Computer.

Lesson 2 - How do computers know what binary patterns translate into what? Well kind of like how we have a dictionary for human languages, a computer has a dictionary for binary digits in terms of characters. The main dictionary that the computer used to use was ASCII or American Standard Code for Information Interchange. We are now using Unicode or Unicode Transformation Format UTF-x for short. This is because Unicode is able to hold more bits, giving the ability to translate a whole lot more characters.

(For more information on binary and Unicode, ASCII I suggest reading [here](https://javarevisited.blogspot.com/2015/02/difference-between-utf-8-utf-16-and-utf.html))

### Is all of that necessary information?

Mmmm, no and yes. But what kind of professionals would we be if we didnt attempt to have a deeper understanding of what is happening under the hood?
___

### Operators &, |, ~, and ^
___

#### &
The AND character is a comparison operator, like the &&. The main difference is that when we use && it will return `true` or `false` depending of the two pieces of information are equal, where as the & characters will return 1 or 0 depending on the same scenario.

Basically the & character is going deeper than the face value of the information being compared.

Example:

```
> 1 && 2
2
> 1 & 2
0

```

Whats happening here?

It is obvious that 1 and 2 are not equivalent. But if  for any reason we want to compare these two characters in a deeper level, all the way down to the binary, we use the single & symbol to get the computer to compare the bits individually.

So `1 && 2` compares 1 and 2 at face value returning 2 while
`1 & 2` compares `00110001` and `00110010`.

___
#### `|`

The same rules apply for the `|` symbol as the & symbol. The main difference is that the `|` symbol is an OR comparison.

Example:

```

> 1 || 2
1
> 1 | 2
3

```

So `1 | 2` will return 3 instead of 0 in the AND(&) comparison? WAIT... WHAT? What happened?

Well lets take a deeper look.

1: 00110001
2: 00110010

when comparing the `|` will return a 1 for each comparison where there is atleast one 1 and 0 and returns 0 when both digits are 0.

So 1 and 2 will return 00110011 or 3.

Isn't that interesting?

___

#### ~

This is the bitwise NOT. What this does is converts 1s to 0s and 0s to 1s. Its finds the complimentary bits.

Example:

```

> ~1
-2
> ~2
-3

```

Lets look at what is happening.

~1: `~00110001` returns `11001110`
~2: `~00110010` returns `11001101`

___

#### ^

This is the XOR comparison. Also called the Exclusive OR comparison. Like the & and `|` comparisons it compares two pieces of information, but compares them in a different way. XOR will compare the bit values one by one as usual but will only return a 1 if the comparison is a 1 to 0. Everything else is returned as a 0.

Examples:

```
> 1^0
1
> 1^1
0
> 1^2
3
> 2^2
0

```

1: 00110001
0: 00110000
returns: 00000001

1: 00110001
1: 00110001
returns: 00000000

1: 00110001
2: 00110010
returns: 00000011

2: 00110010
2: 00110010
returns: 00000000

___
#### Shifting Operators and Bit Manipulation

These concepts are a little more advanced for this blog series but are important nonetheless. Google these bitwise operators if you are curious about them.
