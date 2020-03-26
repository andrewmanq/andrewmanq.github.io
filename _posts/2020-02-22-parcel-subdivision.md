---
layout: post
title: Blocks, Lots, and Props
subtitle: (oh my)
tags: [software, ai, gamedev, architecture, procedural generation, unity, cyberpunk, cityscape, open world, random]
comments: true
---
While the current global pandemic is nothing to be celebrated or trivialized, I have been thankful for the opportunity to work almost uninterruptedly on the city generator.

I showed my girlfriend the picture below, and she told me she enjoyed the pattern so much she would sew it onto a quilt! Unfortunately, most sewing machines don't have the raw power to install unity, so she'll probably have to do it by hand.

![demo](/img/blocks.jpg){: .center-block :}

Each road segment is split down the middle, and each half is handled by the adjacent block. The sidewalk space is wider or narrower depending on the width of the streets. The way I determine how many lanes the road has depends on the order of subdivision: the first cut of the city outline is always the main road, and all branching roads are smaller.

![demo](/img/triangleCity.jpg){: .center-block :}

I added some prototype trees and lamp posts along the roads and it really added more charm than I expected:

![demo](/img/treeCity.jpg){: .center-block :}

Thanks to object batching, I can cram a lot of these details into a single block, and it really helps to give the city a sense of scale.

Expect more frequent posts as I keep myself quarantined -- and check my twitter for video tours of different interesting cityscapes!