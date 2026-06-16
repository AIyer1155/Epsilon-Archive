# Five Points, One Hemisphere

**Category:** Combinatorics
**Difficulty:** P1
**Source:** Putnam 2002 A2
**Tags:** `pigeonhole` `construction` `geometry` `putnam`

---

## Problem

Given any five points on the surface of a sphere, show that some closed hemisphere contains at least four of them.

---

## The Trap

> It's tempting to treat this as a geometry optimization — set up coordinates, worry about worst-case placements, try to push points apart and check that four always cluster. That drags you into casework about angles and positions that never resolves cleanly. The phrase "some closed hemisphere" makes it sound like you must *find* the right hemisphere, when really you get to *build* one to order.

---

## Key Insight

> You choose the hemisphere — so choose its boundary to do free work. Any two of the five points lie on a great circle, and a great circle is the boundary of two closed hemispheres. Put two points *on* the boundary (a closed hemisphere includes its edge), and you've already banked two points for free. That leaves three points and two hemispheres — pigeonhole finishes it.

---

## Solution

Pick any two of the five points. They determine a great circle (if the two points happen to be antipodal, any great circle through both works). This great circle is the common boundary of two closed hemispheres, $H_1$ and $H_2$.

Because the hemispheres are **closed**, both chosen points — which lie on the boundary great circle — belong to $H_1$ *and* to $H_2$. So each hemisphere already contains those two points.

Now look at the remaining three points. Every point of the sphere lies in $H_1$ or $H_2$ (or both, if on the boundary), so each of the three lands in at least one hemisphere. Three points distributed into two hemispheres: by the pigeonhole principle, **some hemisphere receives at least two** of them.

That hemisphere contains those two points plus the two boundary points — four points in all.

$$\boxed{\text{Some closed hemisphere contains at least four of the five points.}}$$

---

## What This Trains

**When you control the construction, build the boundary to bank points.** The decisive move is using the two chosen points as the *edge* of the hemisphere, which only works because "closed" includes the boundary. Reading that word carefully — closed vs. open — is the whole problem; an open hemisphere wouldn't capture the boundary points and the count would fail.

**Pigeonhole is a finishing tool, not a starting one.** The clever part isn't the pigeonhole step (three into two), it's *setting up* the two boxes so the count you need falls out. Most pigeonhole problems are won in how you define the holes, not in the final tally.

---

## Variations

- The same argument generalizes: among any $n+3$ points on an $n$-dimensional sphere, some $n+2$ lie in a closed hemisphere. (Put $n$ points on the boundary great sphere; pigeonhole the remaining three.)
- Can you always do it with *four* points guaranteed in an *open* hemisphere? (No — the boundary trick collapses, and configurations like a regular simplex's vertices block it.)
