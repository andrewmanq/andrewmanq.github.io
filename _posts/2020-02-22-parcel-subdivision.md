---
layout: post
title: Parcel Division
subtitle: Making complex road patterns with simple algorithms
tags: [software, ai, gamedev, architecture, procedural generation, unity, cyberpunk, cityscape, open world, random]
comments: true
---
This post took a while because I spent a month in Japan. Staying in Tokyo gave me a lot of inspiration for this project! Dense neon cities like Tokyo are exactly the feel I'm going for with this project.

![demo](/img/post2img3.jpg){: .center-block :}

One thing I realized (see: last post) is that the only way to manage the complexity of a city generator is to do almost everything recursively. Breaking each area down into divisions, and then subdivisions, and then sub-subdivisions, and all that stuff.

This meant I had to start at the very top level, which is road map and parcel generation. The process is actually pretty straightforward: start with a polygon. Divide the polygon in half (typically along the longest edge). Cut those polygons in half. To introduce variety, I specify how perpendicular to the longest edge the cut happens, and randomize angle variations. The cuts stop when they hit a minimum area, which is divided into building parcels.

I don't plan to implement any curved roads, and yet this seems to generate pretty organic structures. Especially when using different starting polygons like the one below.

![demo](/img/post2img4.jpg){: .center-block :}

I'm using these new polygon operations to re-write the architect as well. Even just extruding the parcels into straight columns makes compelling structures:

![demo](/img/post2img2.jpg){: .center-block :}

And applying a simple window material to them looks pretty imposing:

![demo](/img/post2img1.jpg){: .center-block :}

I'm looking forward to tweaking this code to see what kind of environments it can create.