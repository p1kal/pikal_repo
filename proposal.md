
# Basic framework for tile game

## Repository
<Link to your project's public GitHub respository>
https://github.com/p1kal/pikal_repo.git 

## Description
the basic framework for a tile based dungeon builder game i might make. likely a terrible idea

## Features
- tile deck and related functinality(shuffle, draw to hand, discard from hand)
	- big list or dictionary, then randomize placment of variables in said list.
  - diffrent list/dict for hand
- ability to place tiles on board, with functionality depending on the card
	- first thought is having each tileslot be a variable(or set of variables) that gets overwritten by a placed card. alternatively, if the deck is fully modled instead of being a satistical model, each card could have a tied location value that gets overwritten when placed
- functionaility of said cards
	- if location true and trigered false, do a, b, ...n, to pawn, for every tile in deck, trigger every main step. or use a dictionary to assign output values to a location value, update with tile placment/removal, and standerize effects(more effichent, makes wacky tile effects harder to implement)
- Ability to push tiles on placment
  - step that triggers when placing tile on a filled tileslot. needs 4 direction inputs for where tp push og tile, and a cancel input. hard part is daisy chain pushes
- spawn pawn(s)
  - make a list or dict with a series of stats and variables
- pawn progressive map
  - pull copy of big list or dict of variables for each location value(so they can be marked as various things for pathfinding) from base list
  - record traveled tiles in dict/list
  - at end of cycle, if died false, record seen true tile values to base list
- pawn movment and pathfinding
  - for valid adjacent location values, asign values based on known map, then gen rnd num to decide which direction
- pawn death on health <= 0
  - little text bit depending on which tile killed
- the actual board
  - input board size x by y, make a gird of x+1 by y+1, set outer primter to uninteractable
  - set spawn tile to location value middle of far left(excluding uninteractable border) with math
-  game phases
    - lots of if loops that everthing else gets run through  
- end or continue prompt
  - prompt to end the game or do next round at final phase end
- boss tile
  - has a health value, dies if it takes to much damage from pawns, if dead trigger game over. placed at game start
- graphics framework with placeholder assets
  - will need to be implemented into all steps i think?
-  pawns flee if health gets too low
    - change point values in pathfinding to hevaily prioritze tiles toward entrance/exit.
    - pawn despawns if leaves map, update base map 
    
## Challenges
- previous attempts at brute forcing a deck have failed, reaserch required
- tile functionality implementation is going to be either tedious, inflexible, or a soultion i havent thought of 
- lacks clean linearity in functions, will need to keep going back and forth
- im. unsure of how to do the indivual pawn map instances, speffically in regads to creating new variable sets within play
  - can maybe fake this with x amount of pawn variable sets that get updated on generation of new pawns? will limit maxinum pawns at any given point
- pathfinding will be complicated
- its. a lot. i should probally cut half of this
- graphics scare me 

## Outcomes
Ideal Outcome:
- functional framework from which the rest of the game could be built

Minimal Viable Outcome:
- one of the main systems(pawn, tiles) mostly works, and the other is a broken mess that has to be bypassed to test the other
- and graphics exist to some extent

## Milestones

- Week 1
  1. make the tile deck work
  2. make the board work

- Week 2
  1. make tiles work
  2. start pawns

- Week N (Final)
  1. finish pawns
  2. graphics
