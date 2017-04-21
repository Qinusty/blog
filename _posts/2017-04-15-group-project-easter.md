---
layout: post
title: Group Project EASTER
---

Throughout easter I took a step down and tried to reduce my weekly hours as I
was already approaching 100 hours which I should be at for the start of work
week.

To reach the 100 hour goal I intended to work on the trading logic once Kamyab
had completed the UI window which was completed a week into the Easter break,
allowing me to complete the logic and finalise the FR's before starting work
week. 

Going into work week I have rearranged our Trello to allow us to have a more
focused work week with clear tasks to complete and distribute between the team.

I also discussed with the team what I hoped to get done over work week in our
group chat and brought up what people could be doing over easter to bring their
hours up and get involved with the programming.

Further into the easter break, I decided to fix a bug which had been outstanding for a few weeks.
This bug was a problem with the getValidMoves function and occurred when you were trying to move next to Treasure
Island and another ship was there. According to FR11, you are not allowed to move onto another ship while they are
adjacent to Treasure Island, this was not the case as you could freely move onto them. The fix was simple and just 
required adding another check before adding the tile to the list of valid moves which would be returned.

I also decided to add a chance card, I chose Chance Card #1 as this looked to require some interesting decision making as to
calculate a movement vector away from Treasure Island. I chose to narrow down a list of adjacent tiles by first assuming that if
the list of adjacent tiles has a size of 1, then you are on the corner of the island. After this assumption I could get a movement vector
by grabbing a tile from the list and calculating a vector difference between the x and y on both the ship and tile.

# Work Week Policies
As a group we decided that it is vital that we have a policy in place for
ensuring attendance and punctuality of group members during our brief 5 day work
week to finalise the project. We opted to decide on a Yellow card system which
has been formalised in the minutes by our group leader Alex as 

```
Work Week -> 9:00am to 5:00pm every week day and do not turn up late. 
              Miss a day without VALID reason = yellow card. 
              30+ minutes late = 1 strike, if you get a second strike = yellow card. 
              3+ hours late possible yellow card dependant on reason
```

I believe this is a fair system and will ensure that people are aware of the
consequences which will follow an uninformed missed day.

This being said, Dawid has informed the group of a Hospital appointment on the
Friday of work week and provided sufficient evidence of such. So we will be
ensuring Dawid completes the tasks assigned to him by Thursday and try and get
most things finalised before then anyway.

My aim for work week is to have the more confident programmers spend 1-2 hours a
day assisting the less confident group members to complete tasks and get
involved, this means that we will be working at a slower pace but hopefully the
less confident group members will be able to work more confidently afterwards. 

# Hours Spent


- 2 Hours: Trade Window logic and basic testing.
- 1 Hour: Browsing the project and FR's for tasks to put onto Trello.
- 30 Minutes: Updating Trello and archiving completed tasks.
