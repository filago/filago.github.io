---
title:  "3D Squares Puzzle by DaMert"
layout: post
categories:
  - puzzle
  - python
---

![3D Squares Puzzle](/assets/images/IMG_8250 v3.jpg)

This puzzle recently emerged from a back corner of our games cabinet.  Abandoned years ago, I don't think we ever solved it.

There are 9 tiles to place on the 3x3 board, with the goal of matching all the half-planes between neighboring tiles.

It looks simple enough; how hard could it be to solve?  That depends on how you approach it…


## Two approaches: Brains vs Brawn.

### "Brawn" = Brute Force.  Test every possibility.

With 9 tiles and 4 rotation options each, the number of unique plays is surprisingly large.

(9! x 4^9) = 95.1 Billion possibilities.

If someone actually attempted to try every possibility by hand, they would almost certainly die of old age without finding a solution.  As one Amazon reviewer pointed out, even if you could try one every second it would require **over 3,000 years** to check them all.

Even a computer program could take a long time to evaluate that many plays.  My old PC can evaluate about 20,000 plays per second using python, so it would take almost two months to finish.  This could be improved to some extent with a faster computer or a more efficient program, but I'm more interested in fundamentally better strategies to solve the puzzle.

### "Brains" = Get Smart.  Don't test what can't work.
Here, we skip the possibilities which we can forsee won't produce a solution.

Begin the play on the center square of the 3x3 board, and don't rotate any tiles placed there.  Rotating this tile would not find any new solutions, beyond what you would get by simply rotating the whole board.

Then place the 2nd through 9th tiles, but only if they match to the tiles already on the board.  This builds a solution branch, to be abandoned if no next match is found.

Keep trying branches (and abandoning any that dead-end) until all possible branches have been tested.

It turns out that this eliminates almost all of the brute-force possibilities, requiring only 445 tile placements onto the board.  This a HUGE reduction in effort required.  A python program written to use this method finishes in less than 1/20 of a second, on the same old PC.

I suspect this approach would be reasonable to do by hand.  445 tile placements, at 15 seconds each to allow time for keeping track of the plan, would be about 2 hours.

I would love to know if there's a way to solve it even faster.


## Solutions (Spoiler Alert!)
Here are the only solutions I have found.  They are both similar, with just two corner tiles swapped between them.

![solution 1](/assets/images/IMG_8253 v3.jpg)

![solution 2](/assets/images/IMG_8255 v3.jpg)

I wonder why they designed it with two almost identical solutions - is it not possible to have just one?
