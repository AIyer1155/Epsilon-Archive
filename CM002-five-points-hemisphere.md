# Five Points, One Hemisphere

**Category:** Combinatorics  
**Difficulty:** P1  
**Source:** Putnam 2002 A2  
**Tags:** `pigeonhole` `construction` `geometry`

---

## Problem

Given any five points on the surface of a sphere, show that some closed hemisphere contains at least four of them.

---

## The Trap

> Treating this as a geometry optimization. You set up coordinates, worry about worst-case placements, and try to check that four points always cluster no matter how you spread them. That drags you into casework about angles and positions that never resolves.

---

## Key Insight

> You choose the hemisphere, so choose its boundary to do the work for you. Any two of the five points lie on a great circle, and a great circle bounds two closed hemispheres. Since a closed hemisphere includes its boundary, those two points belong to both. That leaves three points and two hemispheres, and pigeonhole finishes it.

---

## Solution

Pick any two of the five points. They determine a great circle (if the two are antipodal, any great circle through both works). This great circle is the common boundary of two closed hemispheres, $H_1$ and $H_2$.

Because the hemispheres are closed, both chosen points lie on the boundary and so belong to $H_1$ and to $H_2$. Each hemisphere already contains those two points.

Now look at the remaining three points. Every point of the sphere lies in $H_1$ or $H_2$, so each of the three lands in at least one of them. Three points into two hemispheres: by pigeonhole, some hemisphere gets at least two.

That hemisphere holds those two points plus the two boundary points, four in all.

---

## What This Trains

When you control the construction, build the boundary to carry points for you. The decisive move is using the two chosen points as the edge of the hemisphere, which only works because "closed" includes the boundary. Reading that word carefully is the whole problem. An open hemisphere would miss the boundary points and the count fails.

Pigeonhole is a finishing tool, not a starting one. The clever part isn't the three-into-two step, it's setting up the two boxes so the count you need falls out. Most pigeonhole problems are won in how you define the holes.

---

## Variations

- The same argument generalizes: among any $n+3$ points on an $n$-dimensional sphere, some $n+2$ lie in a closed hemisphere. Put $n$ points on the boundary great sphere, then pigeonhole the remaining three.
- Can you always guarantee four points in an *open* hemisphere? The boundary trick collapses, and configurations like the vertices of a regular simplex block it.
