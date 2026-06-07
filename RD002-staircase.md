# The Staircase

**Category:** Recursive Decomposition  
**Difficulty:** P1  
**Source:** Classic / LeetCode 70  
**Tags:** `recurrence` `fibonacci` `first-step-analysis`

---

## Problem

You're climbing a staircase with $n$ steps. Each move you can climb 1 or 2 steps. How many distinct ways can you reach the top?

---

## The Trap

> Trying to enumerate paths directly for large $n$. The structure is recursive the last step determines everything.

---

## Key Insight

> To reach step $n$, you came from either step $n-1$ (took 1 step) or step $n-2$ (took 2 steps). So the number of ways to reach $n$ is exactly the number of ways to reach $n-1$ plus the number of ways to reach $n-2$.

---

## Solution

Let $f(n)$ = number of ways to climb $n$ steps.

Base cases: $f(1) = 1$, $f(2) = 2$.

Recurrence: $f(n) = f(n-1) + f(n-2)$.

This is the Fibonacci sequence (shifted by one):

| $n$ | $f(n)$ |
|---|---|
| 1 | 1 |
| 2 | 2 |
| 3 | 3 |
| 4 | 5 |
| 5 | 8 |
| 10 | 89 |

**Answer:** $f(n) = F_{n+1}$ where $F_k$ is the $k$-th Fibonacci number.

---

## What This Trains

First-step analysis creating a recurrence, and recognizing Fibonacci structure. The broader lesson: when a problem has a "last decision" that determines how you got there, condition on it. This is also a standard dynamic programming pattern.

---

## Variations

- You can climb 1, 2, or 3 steps at a time. How many ways now?
- How many ways if you can't take two consecutive 2-step jumps?

