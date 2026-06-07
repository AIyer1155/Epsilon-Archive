# The Coin Flips

**Category:** Symmetry  
**Difficulty:** P1  
**Source:** Classic probability  
**Tags:** `binomial` `combinations` `symmetry`

---

## Problem

You flip a fair coin 10 times. What is the probability of getting exactly 5 heads?

---

## The Trap

> Just writing $\frac{1}{2}$ because "5 heads out of 10 is the most likely outcome so it's probably around half." The most likely outcome is not necessarily a likely outcome.

---

## Key Insight

> Count the favorable sequences over total sequences. Total is $2^{10}$, favorable is $\binom{10}{5}$ — the number of ways to place 5 heads in 10 flips.

---

## Solution

Total equally likely outcomes: $2^{10} = 1024$.

Sequences with exactly 5 heads: $\binom{10}{5} = 252$.

$$P(\text{exactly 5 heads}) = \frac{252}{1024} = \frac{63}{256} \approx 24.6\%$$

Even the most likely outcome only happens about 1 in 4 times.

---

## What This Trains

Two things: the binomial probability formula, and the intuition that "most likely" doesn't mean "likely." In finance this matters constantly — the modal outcome of a distribution can still have low probability if the distribution is spread out.

---

## Variations

- What's the probability of getting *at least* 8 heads?
- For large $n$, the probability of exactly $\frac{n}{2}$ heads in $n$ flips is approximately $\sqrt{\frac{2}{\pi n}}$. Verify this makes sense for $n = 10$.

