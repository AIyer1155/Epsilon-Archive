# The Dice Game

**Category:** Expected Value  
**Difficulty:** P1  
**Source:** Classic probability  
**Tags:** `geometric-distribution` `expected-value`

---

## Problem

You roll a fair six-sided die repeatedly until you roll a 6. What is the expected number of rolls?

---

## The Trap

> Summing an infinite series directly. You can, but there's a cleaner one-line argument.

---

## Key Insight

> Each roll is independent. You succeed with probability $\frac{1}{6}$ each time. This is just a geometric distribution and the expected value of a geometric with success probability $p$ is $\frac{1}{p}$.

---

## Solution

Let $X$ = number of rolls until the first 6. Then $X \sim \text{Geometric}\left(\frac{1}{6}\right)$.

$$E[X] = \frac{1}{p} = \frac{1}{1/6} = 6$$

**First-step derivation if you don't want to invoke the formula directly:**

Let $E$ = expected rolls. On the first roll, you either roll a 6 (probability $\frac{1}{6}$, done in 1 roll) or you don't (probability $\frac{5}{6}$, and you're back to the start):

$$E = \frac{1}{6}(1) + \frac{5}{6}(1 + E)$$

$$E = 1 + \frac{5}{6}E \implies \frac{1}{6}E = 1 \implies E = 6$$

---

## What This Trains

Recognizing geometric distributions on sight and knowing $E[X] = \frac{1}{p}$. Also the first-step derivation, which is the move when the distribution isn't obvious.

---

## Variations

- Expected rolls until you see two 6s in a row?
- You win \$10 if you roll a 6 within 3 rolls, pay \$2 otherwise. What's the fair price to play?

