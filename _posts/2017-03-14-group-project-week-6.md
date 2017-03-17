---
layout: post
title: Group Project Week 6
---

This week I was assigned the task of throwing together some diagrams for the
Design Document which is due in the next few weeks. I decided to start with the
State diagram and first draw out the diagram with the actual states used in the
implementation. This gave an overview for those who may be working with the
project and needed to understand the changes in ingame states.

I also made a full turn state diagram which shows states which the game may go
through indirectly and what order things happen. This sort of diagram is more
appropriate to be shown to a less technical member of the team and perhaps the
client as it allows them to see what the game goes through on each turn. This
could possibly even be shown to a player to show them what happens during their
turn.

I decided that it would also help to do some sequence diagrams, to show the
processes in a more technical form, showing what function calls happen
throughout specific situations within the program. So far I have done one for
the movement event which shows what the program needs to do to move a ship once
a user has given input. I have also done one for the initialisation of the UI
and for combat.


Furthermore, I realised how I could use design patterns to simplify some of the
code in the Board class and allow for the code to be more maintainable and
reusable, while being modifyable via config files through CSV for the map and a
properties file for the tile type strings.

# Time sheet:


- 5 Hours: Doing various diagrams for the design spec document.
- 5 Hours: Refactoring code including implementing Design patterns.
