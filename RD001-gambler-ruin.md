# Gambler's Ruin

**Category:** Recursive Decomposition  
**Difficulty:** P2  
**Source:** Classic / Feller  
**Tags:** `first-step-analysis` `recurrence` `random-walk`

---

## Problem

You start with \$k. Each step: win \$1 with probability $p$, lose \$1 with probability $q = 1-p$. Game ends when you hit \$N (you win) or \$0 (you're done). What's the probability you reach \$N?

---

## The Trap

> Counting paths directly. The game can last arbitrarily long, so you're summing an infinite series that gets ugly fast. First-step analysis is the move.

---

## Key Insight

> Condition on the first step. Your win probability from position $k$ depends only on your win probability from $k+1$ and $k-1$ — that's a recurrence you can actually solve.

---

## Solution

Let $P_k$ = probability of reaching $N$ from position $k$. Boundaries: $P_0 = 0$, $P_N = 1$.

First step gives:

$$P_k = p \cdot P_{k+1} + q \cdot P_{k-1}$$

The characteristic roots are $r = 1$ and $r = q/p$.

**If $p \neq q$:**

$$P_k = \frac{1 - (q/p)^k}{1 - (q/p)^N}$$

**If $p = q = \frac{1}{2}$:**

The two roots collapse, so the general solution shifts to $P_k = A + Bk$. Boundaries give $P_k = \frac{k}{N}$.

Fair game, start at \$50, target \$100 → you win exactly half the time. Makes sense.

---

## What This Trains

First-step analysis: condition on the first event, write a recurrence, solve it. This is the core move for random walks and Markov chains, and it shows up in a lot of interview problems that look nothing like this one on the surface.

---

## Variations

- What's the expected *duration* of the game?
- What happens as $N \to \infty$? When does the gambler survive with positive probability?
- You have 100 units of capital, each trade ±1. What $p$ gives you a 90% chance of doubling before ruin?

