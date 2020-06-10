---
layout: post
title: PhaserJS Day Zero
author: Anthony Oglesby
date: 2020-06-10 13:36:51 -0400
---


# PhaserJS
## Day 0

**Intro**

- I am going to be pretty much using this as a journal of sorts to document my journey learning PhaserJS. This is for two reasons.
	1. This will serve as my reference guide to everything I have learned and act as my notes, thoughts, etc.
	2. This may give insight into anyone else in the universe possibly wanting to get into learning PhaserJS. They above is true for me, however it can be true for someone else as well.

**Day 1**

Of course the best way to learn any tech stack / framework is to go to the [source](https://phaser.io/tutorials/getting-started-phaser3).
This link will take you to the PhaserJS guide to getting started.

It literally guides you through installation and setup of a development environment for Phaser.

That being said this is where I will be starting off today.

So right off the bat I ran into something I have never thought about. Using a web server. From my very basic knowledge a web server is something like Puma for Ruby. The guide explains in detail why a web server is useful (mainly for security reasons), and while I dont know much about the nitty gritty of it all I will have to come back to it later. Maybe Ill write a blog entry about it sometime soon. They have also listed a few suggestions for web servers to set up for Windows, Mac, etc. I use Linux and since I am not advanced in this particular subject I am going to go with http-server for node.js. This is described as a zero-configuration simple command line http server. Sounds perfect for my needs right now.

So lets get http-server set up.

Here are the steps I followed.

1. Go to this [page](https://www.npmjs.com/package/http-server).
2. READ THE ENTIRE README AND INSTALL GUIDE!!! (Its boring, but read it before you install or attempt to set up anything.)
3. Open a terminal and enter `npm install --global http-server`
	- If you don't have npm I suggest you get it. It is pretty much required to use Javascript. Install instructions [here](https://www.npmjs.com/get-npm)

That's it for installation.

The next step is our editor. If you are like me and already have an editor then we can skip this step. If you don't have an editor I recommend [Atom](https://atom.io/) and [VS code](https://code.visualstudio.com/). They are both editors that you can easily learn to use and continue learning as you get more advanced **AND THEY ARE FREE**. I personally use Atom, because I love supporting free, open source, community driven software.

Now its time to set up ***PhaserJS***.

Who's excited?!?!

Here are the steps I followed:

1. Opened this [link](https://phaser.io/download/stable).
2. READ EVERYTHING ON THIS PAGE FIRST! (As always it is important to read first install later.)
2. Open your terminal again and paste `npm install phaser@3.23.0`

And that's it. Done!

Now the fun begins. We get to make a Hello World app using PhaserJS.

These are the steps I followed:

1. Open terminal and `cd Desktop`
2. Create a folder to house any Phaser projects. `mkdir PhaserJS_stuff`
3. Change your directory to the new folder. `cd PhaserJS_stuff`
4. Create an html file called index.html. `touch index.html`
5. Now we can open our editor from  the directory we are already in by `atom .` If you use another editor use that editors specified command. For example Sublime uses `subl` and VS Code uses `code`
6. On PhaserJS's [guide](https://phaser.io/tutorials/getting-started-phaser3/part5) There is html code they want you to copy and paste into the html file you just created. So... do it.
7. Now back in your terminal, make sure you are in you PhaserJS_stuff folder (or whatever you decided to name it) and type `http-server`.
8. You should get something like this: <br><img src="/assets/images/phaserterminal.png" width="400px">
9. Now if you open your web browser and go to `http://localhost:8080/` you should see:<br><img src="/assets/images/PhaserJS.png" width="400px">

There you go. That's pretty rad.

Now that We have PhaserJS up and running on our machine we can start actually learning how to use this crazy framework. I suggest if you don't know Vanilla Javascript already that you try your hand at it first. Learn some foundational stuff before getting into frameworks.

That concludes my Day Zero. We got pretty much every thing we need to start learning PhaserJS. Looking forward to future projects.
