---
layout: post
title: Group Project Week 9
---

This week I was tasked with working on the design doc once again, I decided to tackle the significant algorithms section and write a piece of pseudo-code about the algorithm used to select valid tiles. 
I was also tasked with implementing the functionality of flat island and ship interactions with it. This was quite simple as the code for island detection was already there, I just had to modify it from treasure island to Flat Island and get the adjacent ship to withdraw the cards and up to 2 items of treasure.

Further into the week, I experimented with using gif's for the sea tiles, this lead me to a realisation of how inefficient our game was at loading image files, each image would be instantiated within the tile constructor, meaning that for each of the 350~ sea tiles which were identical and using the exact same image we would have an image stored in memory. This was not a huge deal when using PNG's as it still fit within the default Java heap size, however it still wasted a large amount of memory. So I set out this fix this, I decided to implement a Graphic Loader class which used the singleton design pattern to insure that the class was only instantiated once and would manage all images used within the game, storing them in instance varaibles and leaving them accessable through getter methods. This means that now, each constructor can request the image appropriate to the class but only keep a reference to the pre-initialised image in memory.

To ensure that our images did not casue any issues down the line I also wrote some JUnit tests to check that the Graphic Loader class had loaded all of these images successfully. This ensures that we never break a path to an image and have it go unnoticed.

# Time Spent:

- 3 Hours: Implementing Graphic Loader
- 2 Hours: Implementing Flat Island functionality
- 2 Hours: Design Document
- 1 Hour: Further documenting code
- 1 Hours: Implementing Tests
