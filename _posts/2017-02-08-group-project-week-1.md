---
layout: post
title: 'Group Project: Week 1'
---

# Tasks: 

- [x] Program Architecture initial mockup (with Alex)

This week I was assigned the task of creating the initial architectural design with Alex, we decided to create a Google doc, so that we could collaborate our initial ideas onto a page.
I threw down my ideas of individual classes and what each would contain, I had implemented similar game like architectures in the past so I took inspiration from them. Alex wrote 
some comments over my ideas, pointing out a few changes that could be made and what could be added including ways we could implement the treasure and its value. I think our initial design
should get us off to a good start, we may uncover some weaknesses during the implementation, however we can adjust as necessary. 

After meeting with my group on Thursday, discussing what we had managed to do so far I decided that I would give JavaFX a go to explore the possible ways we could implement our rough UI design. I found that using a canvas in JavaFX, I could draw the grid on each iteration of the game cycle and update it with all objects in the game state such as the Board and Players. I could also draw an interface as we had designed, writing text and displaying the port assigned to each player. This short experience made me realise that for the final implementation it would be much cleaner if we had a wrapper around the JavaFX canvas to allow us to draw things to the grid in a much more simple manner. Avoiding the use of coordinates on the window, and using grid coordinates.

# Weekly Diary
Time Spent: 


- 30 Minutes task: Share initial thoughts on project architecture with Alex via Google Docs and iron out any problems.
- 1 Hour task: Create a mock up JavaFX UI for meeting.
