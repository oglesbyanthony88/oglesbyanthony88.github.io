---
layout: post
title: PhaserJS Day One
author: Anthony Oglesby
date: 2020-06-11 13:36:51 -0400
---

# PhaserJS

## Day 1

**Intro**

- While I was looking at the Phaser Official website, I found that they had a complete video course for learning PhaserJS at [Zenva Academy](https://academy.zenva.com/product/complete-phaser-game-development-bundle/). Now Zenva is not free but I managed to stumble on a discount so the first month of ther service was only $14.99 vs the normal $19.99. Lets be honest here. I'm all about free or as cheap as possible and when we are talking about a few dollars to get a structured way to learn something I'm pretty much for it. I am a visual learner so I love learning from videos. That being said. There are always free ways to learn. They sometimes just require a bit more work on your end.

**Day 2**

The first concept That I find very interesting is a *Game Design Document*. Apparently this is common in the game industry and is used to describe all of the core aspects of your game. Everything from concept art, to description of game play is in the document. I would love to go into more detail about this, but I think this will end up being a separate blog post as I am following tutorials, and it doesn't seem to be a huge priority in the learning process at the moment. This will be better suited for when I get closer to creating my own games.
<br>
<img src="/assets/images/phaserday1/gddsample.png" width="400px">

I do want to talk about two things that I learned about today.

1. PhaserJS Life cycle of a Scene
2. Coordinate System

### Life cycle of a Scene

- Before we can talk about the Phaser JS Life Cycle of a Scene we need to talk about what a Scene is.
- A **Scene** is where everything in a game will take place. All characters, enemies, backgrounds, etc. will be loaded into the scene.
- In order to set up a scene in PhaserJS follow these steps.
	1. Assuming you have a Game Folder already created with your js folder and an index.html, go ahead and open your js folder. Here if you dont already have it, go ahead and place the phaser.js file downloaded from [here](https://github.com/photonstorm/phaser/releases/download/v3.23.0/phaser.js). - (*note: this is a download link*) - I also suggest saving this file in a separate folder somewhere safe, because this is the source code and has comments that explains what everything does.
	2. Then create a new file called game.js
	3. Open game.js in your code editor and lets start coding. We first need to create the scene. <br><img src="/assets/images/phaserday1/createscene.png" width="400px">
	4. Now we need to configure the scene. <br><img src="/assets/images/phaserday1/sceneconfig.png" width="400px">
	5. And the last thing in game.js is to create the game, and pass in the scene configuration. <br> <img src="/assets/images/phaserday1/creategamescene.png" width="400px">
	6. Now before we can load this into a browser we need to go to our index.html and change a few things.<br><img src="/assets/images/phaserday1/indexscene.png" width="400px"><br>We are jsut adding two lines to the body<br> `<script src="js/phaser.js"></script>` <br>and <br>`<script src="js/game.js"></script>`
	7. Now lets open up terminal and cd into our Game Folder.
	8. Use `$ http-server` to start the web server and then copy the url into the browser. - (*note: I found that the first url worked best for me. http://127.0.0.1:8080. I found that just using localhost:8080 and http://192.168.1.6:8080 ended up not setting the proper config parameters. So try using localhost and the two addresses listed in http-servers available on list.*) You should see something like this:<br><img src="/assets/images/phaserday1/scenebrowser.png" width="400px">

Look at that. We made a simple scene. Looks pretty boring right now but we havnt added anything to it. But before we add anything to it, lets finally talk about life cycle methods for a scene.
<br>
<img src="/assets/images/phaserday1/scenelifecycle.png" width="600px">
<br>

There are four lifecycle methods for a scene.

1. The `init()` method is called and used once to initialize parameters of your scene.
2. The `preload()` method is used to preload all of the assets your scene will be using. These assets are loaded into the memory so they can be used immediately.
3. The `create()` method is where the assets will be created and rendered to the screen.
4. Finally the `update()` method is called at every frame during game play. Typically used when a game needs to be checked consistently.


### Coordinate System

Remember in school when you had to make graphs and draw dots on those graphs. There was the X and Y axis. All that fun stuff. Sorry, didn't mean to bring up bad memories...

Well not really. Finding coordinates for where things need to go on a scene is pretty much like using a graph. the big difference is that while in school graphs looked like this: <br><img src="/assets/images/phaserday1/schoolgraph.png" width="400px"><br> They now look like this: <br><img src="/assets/images/phaserday1/gamegraph.png" width="400px"><br> The big difference is that 0, 0 starts in the top left corner of the graph.

Now when we want to load something into the scene we cant just say background.image(0, 0). While this will work it will render the background off center.
<br>
<img src="/assets/images/phaserday1/offcenterscene.png" width="400px">
<br>

To fix this issue we can do several things. But first you need to know the center of your scene. You can find this by Height/2 and Width/2. So if Width = 640 and Height = 360 we know that the center for the scene is (320, 180). Also we need to keep in mind that the img or asset you want rendered will render to that point at its center.

1. We can change the coordinates so background.image(0, 0) is now background.image(320, 180) or background.image(640/2, 360/2).
2. We can change the origin point of the asset, so that instead of rendering to the scene at its center point it will render at its top left corner point. this can be done by creating the asset `let bg = this.add.background(0, 0)` and then `bg.setOrigin(0, 0)`.


This was just a basic run down of both Life Cycle Methods of a scene and how to render assets to the scene using the Game Coordinate System. Hope this helps everyone as much as it helped me.
