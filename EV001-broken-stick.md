# The Broken Stick

**Category:** Expected Value  
**Difficulty:** P1  
**Source:** Classic probability / folklore  
**Tags:** `linearity` `symmetry` `uniform-distribution`

---

## Problem

A stick of length 1 is broken at a point chosen uniformly at random. What is the expected length of the shorter piece?

---

## The Trap

> You set up $\int_0^1 \min(x, 1-x)\, dx$ and split at $\frac{1}{2}$. It works, but it's easy to mess up the split under pressure.

---

## Key Insight

> The two pieces are symmetric around $\frac{1}{2}$, so neither is systematically longer. You can just integrate directly since the symmetry makes both halves of the integral identical.

---

## Solution

Let $X \sim \text{Uniform}(0,1)$ be the break point. The shorter piece has length $\min(X, 1-X)$.

$$E[\min(X, 1-X)] = \int_0^{1/2} x\, dx + \int_{1/2}^1 (1-x)\, dx = 2\int_0^{1/2} x\, dx = 2 \cdot \frac{1}{8} = \frac{1}{4}$$

The shorter and longer pieces add to $\frac{1}{4} + \frac{3}{4} = 1$, which is what you'd expect.

---

## What This Trains

Checking your answer against a complementary quantity before you commit to it. The two pieces have to sum to 1, so the longer piece falling out as $\frac{3}{4}$ confirms the shorter one.

---

## Variations

- Break at *two* independent uniform points. Expected length of the shortest of the three pieces? (Answer: $\frac{1}{9}$.)
- You win \$1 if the shorter piece exceeds $\frac{1}{3}$. What's the fair price for this bet?

