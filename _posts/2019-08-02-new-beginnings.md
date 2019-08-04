---
layout: post
title: The Anatomy of a Street Block
subtitle: War, pestilence, death, and code revision
tags: [software, ai, gamedev, architecture, procedural generation, unity, cyberpunk]
comments: true
---
![demo](/img/diagram1.jpg){: .center-block :}

The most important ability of a competent programmer is breaking complex problems into smaller, less daunting pieces.

Unfortunately, this process occurred to me at a relatively inopportune moment when

A. I was naked (in the shower) and

B. I had already half-finished the program in question.

My [procedural city generator](https://andrewmanq.github.io/2019-07-09-proj-1/) in its current form resembles one of those glass-paneled open-air desktop PC builds. It looks nice, but falls apart if you throw anything at it. All of the components are very separate from each other, but are held together by a spiderweb of loose data connections.

The program first generates all of the roads at once, in one giant mesh. While this works wonders for the post-generation performance, it also adds the complexity of communicating where all of the buildings are supposed to be wedged between them. An added complication is that those in-between bits have to adhere to an already-existing road. This leaves out any complexities like widening the roads for right-turn lanes, or adding coves of roadside parking spaces.

As of this blog post, my buildings generate their own sidewalks, and are called by an outside function to be created. Their stylistic appearances must be hard-programmed by a separate entity if the city is to hold any visual consistency.

As I stood in the steamy shower, I realized how overcomplicated this was. My new proposed system (aptly titled *post-shower alpha 0.1*) will generate the roads and sidewalks block-by-block. An added bonus of this is that I can keep slapping blocks onto existing cities like Phil Swift smacking flex tape onto a gaping flesh wound. The block itself only has to worry about making the right-hand lane of its adjacent roads (in clockwise order around the polygon).

Each block will be a puzzle-piece, fitting snugly against its roadside neighbors. From there, sidewalks are created. Then the alleyways. And finally, the buildings. A Russian nesting-doll datatype will house these objects layer by layer; roads being a large babushka encapsulating its Siberian children (pavement, parcels, storefronts, and buildings respectively).

Unity has a new burst compiler and job system that I hope to take full advantage of. This way I can multithread everything to make it even faster.

Now the task I have ahead of me is trivial - completely redesign the system I've been working on for half a year. Seems pretty easy, right?