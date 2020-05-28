---
layout: post
title: Quick Update - Procedural Architecture
subtitle: My second try at procedural buildings
tags: [software, ai, gamedev, architecture, procedural generation, unity, cyberpunk, cityscape, open world, random]
comments: true
---

Since my last post, Building generation has been my sole focus.

![demo](/img/post5img1.jpg){: .center-block :}

I've made a shader for the windows that has interior projection - it appears as though there are rooms inside the windows, but they are actually a cube texture applied to some trig functions. My shader also uses the building's position as a unique identifier, so each building has a unique color (even though they all use the same material!) Basically, the buildings have a decent amount of detail for very low overhead. I can fit about a thousand buildings in a scene before I dip below 60 frames per second.

![demo](/img/post5img3.jpg){: .center-block :}

Thanks to the modularity of my previous code, I repurposed my city block division system to make building segments. Instead of the previous AI architect, which relied on taking a building's outline and modifying it recursively, this one is entirely non-destructive. Each building is a list of polygons that gets extruded upwards, and may or may not be generated depending on what floor it's on.

![demo](/img/post5img2.jpg){: .center-block :}

Notice in the picture above that the center building has a hole in it. This is completely intentional, and fits with the sci-fi theme I'm going for. Multiple people have asked me if this was a bug, but these kinds of buildings are more common than you might think! There are tons of 'doughnut shaped' skyscrapers going up in the present day, especially in china.

![demo](/img/post5img4.jpg){: .center-block :}

Each building in the above screenshot is using the same "architectural style" struct to generate it's appearance, and yet they are all fairly unique shapes. I've wasted a lot of time just generating different seeds and seeing how they turn out. My favorite ones are those with winding tunnels through the buildings that provide endless explorability: one seed had a massive building in the middle that was completely hollow - a cavernous atrium with multiple entrances. I think I'm on to something special here, and it's only going to get more complex and varied from here on out.