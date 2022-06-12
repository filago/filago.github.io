---
title:  "3D Squares Puzzle"
layout: post
categories:
  - puzzle
  - python
---

![3D Squares Puzzle](/assets/images/IMG_8250 v3.jpg)

This puzzle from DaMert Company recently emerged from a back corner of our games cabinet.  Abandoned years ago, I don't think we ever solved it.

There are 9 tiles to place on the 3x3 board, with the goal of matching all the half-planes between neighboring tiles.

It looks simple enough; how hard could it be to solve?  That depends on how you approach it…

## Two approaches: Brains vs Brawn.

### "Brawn" = Brute Force.  Test every possibility.

With 9 tiles and 4 rotation options each, the number of unique plays is surprisingly large.

(9! x 4^9) = 95.1 Billion possibilities.

If someone actually attempted to try every possibility by hand, they would almost certainly die of old age without finding a solution.  As one Amazon reviewer pointed out, trying one attempt every second would require **over 3,000 years** to check them all.

Even a computer program could take a long time to evaluate that many plays.  My old PC can evaluate about 20,000 plays per second using python, so it would take almost two months to finish.  This could be improved with faster programs and computers, but I'm more interested in fundamentally better strategies to solve the puzzle.

### "Brains" = Get Smart.  Don't test what can't work.
Here, we skip the possibilities which we can forsee won't produce a solution.

Begin the play on the center square of the 3x3 board, and don't rotate any tiles placed there.  Rotating this tile would not find any new solutions, beyond what you would get by simply rotating the whole board.

Then place the 2nd through 9th tiles, but only if they match to the tiles already on the board.  This builds a solution branch, to be abandoned if no next match is found.

Keep building branches (and abandoning any that dead-end) until all possible branches have been tried.

It turns out that this eliminates almost all of the brute-force possibilities, requiring only 445 tile placements onto the board.  This a HUGE reduction in effort required.  A python program written to use this method finishes in less than 1/20 of a second, on the same old PC.

I'm tempted to go through the effort to solve it by hand using this method, at least long enough to estimate how long it would take to complete.  And I would love to know if there's a way to solve it even faster.

## Solutions
Here are the only two solutions I have found.  They are almost identical, with the upper-right and lower-left tiles swapped.

![solution 1](/assets/images/IMG_8253 v3.jpg)

![solution 2](/assets/images/IMG_8255 v3.jpg)
