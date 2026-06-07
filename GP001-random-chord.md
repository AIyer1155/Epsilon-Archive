# The Random Chord

**Category:** Geometric Probability  
**Difficulty:** P2  
**Source:** Bertrand's Paradox / Classical  
**Tags:** `geometric-probability` `paradox` `measure`

---

## Problem

A chord is drawn at random in a unit circle. What is the probability its length exceeds $\sqrt{3}$?

---

## The Trap

> Assuming "at random" has a single obvious meaning. It doesn't — this is Bertrand's Paradox. The answer depends on how you define "random chord," and three natural definitions give three different answers.

---

## Key Insight

> There is no unique answer. The problem is ill-posed until you specify the probability model. Each of the three methods below is internally consistent.

---

## Solution

Note: a chord has length $> \sqrt{3}$ iff it's longer than the side of an inscribed equilateral triangle.

**Method 1 — Random endpoints:** Pick two points uniformly on the circle. Fix one at the top. The chord exceeds $\sqrt{3}$ when the second point falls in the arc subtended by the opposite third of the circle.

$$P = \frac{1}{3}$$

**Method 2 — Random midpoint:** A chord is determined by its midpoint. Pick the midpoint uniformly over the disk. The chord exceeds $\sqrt{3}$ iff the midpoint lies within a circle of radius $\frac{1}{2}$ centered at the origin (this comes from the geometry of the inscribed triangle).

$$P = \frac{\pi (1/2)^2}{\pi (1)^2} = \frac{1}{4}$$

**Method 3 — Random radius:** Pick a radius at random, then pick a point uniformly on that radius as the midpoint of a perpendicular chord. The chord exceeds $\sqrt{3}$ iff the midpoint is within the inner half of the radius.

$$P = \frac{1}{2}$$

Three answers: $\frac{1}{3}$, $\frac{1}{4}$, $\frac{1}{2}$. All correct given their model.

---

## What This Trains

"Uniform at random" is not self-defining on continuous spaces — you need to specify the measure. This is directly relevant to model risk: two quant models can both be "reasonable" and give completely different answers. Always ask what the probability space is before computing.

---

## Variations

- Which method is the "right" one if you physically drop a straw randomly onto a circle drawn on the floor?
- Can you construct a fourth method that gives $P = \frac{1}{5}$?

