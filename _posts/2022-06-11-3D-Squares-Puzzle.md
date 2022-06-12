---
title:  "3D Squares Puzzle"
layout: post
categories:
  - puzzle
  - python
---

![3D Squares puzzle](/assets/images/IMG_8250 v3.jpg)

This puzzle from DaMert Company recently emerged from a back corner of our games cupboard.  Abandoned years ago, I don't think we ever solved it.

It is deceptively simple to explain. There are 9 tiles to place on the 3x3 board, and the idea is to match all the half-planes between neighboring tiles.

So how hard could it be?  It turns out that depends on how you approach it…

## Brains vs Brawn: Two approaches

### The "brawn" method.
The brute force approach: Test every possibility.

With 9 tiles and 4 rotation options each, the number of unique plays is overwhelming.

#### (9! * 4^9) = 95.1 Billion possibilities

If someone actually tried this approach by hand and was too stubborn to give up or try a better method,
they would almost certainly die of old age without finding a solution.  As one Amazon reviewer pointed out, trying 1 attempt every second would require over 3,000 years to check them all.

Even a computer program could take a long time to evaluate that many plays.  I created a python program for it, which evaluates about 20,000 such plays per second, running on a 12 year old PC.  This would take almost 2 months to finish.

### The "brains" method.
Add some logic to eliminate possibilities that can't produce a solution.

Begin the play on the center square of the 3x3 board, and don't rotate any tiles placed there.  There would be no new solutions found by rotating a tile at this position, beyond what you would get by simply rotating the whole board.

Then place the 2nd through 9th tiles, following a consistent location sequence, but only if they match to the tiles already on the board.  This builds a solution branch, to be abandoned if no next match is found.

Keep building branches (and abandoning any that dead-end) until all possible branches have been tried.

It turns out that this eliminates almost all of the brute-force possibilities, requiring only 445 tile placements onto the board.  This a HUGE reduction in effort required.  A python program written to use this method finishes in less than 1/20 of a second, on the same old PC.

I'm tempted to go through the effort to solve it by hand using this method, at least long enough to estimate how long it would take to complete.  And I would love to know if there's a way to improve on it to speed up the solution even more.

## Solutions
Here are the only two solutions I have found.  They are almost identical, with the upper-right and lower-left tiles swapped.

![solution 1](/assets/images/IMG_8253 v3.jpg)

![solution 2](/assets/images/IMG_8255 v3.jpg)
