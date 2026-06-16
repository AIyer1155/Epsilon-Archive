# Full Sequences

**Category:** Combinatorics
**Difficulty:** P2
**Source:** Classic combinatorics (full / staircase sequences)
**Tags:** `bijection` `binary-strings` `combinatorics`

---

## Problem

A non-decreasing sequence of $n$ positive integers is called **full** if, for each integer $k \ge 2$ that appears in the sequence, the number $k-1$ also appears.

Find the number of full sequences of length $n$.

---

## The Trap

> Counting directly by casework — fix the maximum value $k$, then count how to place values $1, \ldots, k$ so each appears at least once — leads straight into Stirling-number territory and a sum you don't want to evaluate. You're counting the right object the hard way. The "full" condition also looks like a complicated constraint, when it's really just saying the values used form an unbroken block $\{1, 2, \ldots, k\}$ with no gaps.

---

## Key Insight

> A non-decreasing full sequence is completely determined by **how many times each value appears**. Recording those counts $(a_1, a_2, \ldots, a_k)$ — with each $a_i \ge 1$ and $a_1 + \cdots + a_k = n$ — is exactly a **composition of $n$**. And compositions of $n$ are counted by the gaps between $n$ items: each of the $n-1$ internal gaps is either a "cut" or not, giving $2^{n-1}$.

---

## Solution

**Why the sequence is its multiset.** The sequence is non-decreasing, so once you know the multiset of values, the order is forced — sort them. So counting full sequences means counting valid multisets.

**Unpacking "full".** If the largest value used is $k$, then fullness forces every one of $1, 2, \ldots, k$ to appear at least once (any missing value below $k$ would orphan the value above it). So the set of values used is exactly $\{1, 2, \ldots, k\}$ — a clean initial block.

**The bijection with compositions.** Let $a_i \ge 1$ be the number of times value $i$ appears, for $i = 1, \ldots, k$. Then
$$a_1 + a_2 + \cdots + a_k = n, \qquad a_i \ge 1.$$
This is precisely a **composition of $n$**: an ordered tuple of positive integers summing to $n$. The map is a bijection — a full sequence gives its count vector, and a composition $(a_1, \ldots, a_k)$ rebuilds the unique sorted sequence (value $i$ written $a_i$ times).

**Counting compositions.** Line up $n$ units in a row, with $n - 1$ gaps between consecutive units:
$$1 \;\square\; 1 \;\square\; 1 \;\square\; \cdots \;\square\; 1.$$
A composition corresponds to choosing which gaps are "breaks." Each of the $n-1$ gaps is independently a break or not, so there are
$$2^{n-1}$$
compositions, hence $2^{n-1}$ full sequences.

$$\boxed{2^{n-1}}$$

**Sanity check.** $n=1$: just $[1]$, count $1 = 2^0$. $n=2$: $[1,1]$ and $[1,2]$, count $2 = 2^1$. $n=3$: $[1,1,1], [1,1,2], [1,2,2], [1,2,3]$, count $4 = 2^2$. Matches.

---

## What This Trains

**Bijection thinking** — when a direct count produces a messy sum (here, Stirling numbers), ask what *simpler* object you're secretly counting. Recognizing the count vector of a non-decreasing sequence as a composition of $n$ collapses the whole problem to a known $2^{n-1}$.

**The stars-and-bars / gaps model** for compositions is worth having at your fingertips: compositions of $n$ into any number of positive parts ↔ subsets of the $n-1$ internal gaps ↔ binary strings of length $n-1$, all counted by $2^{n-1}$. This pattern recurs constantly in combinatorics.

---

## Variations

- **Drop "non-decreasing."** If the sequence may be in any order (the values used still forming a block $\{1,\ldots,k\}$), the count is no longer $2^{n-1}$ — it's the **ordered Bell number** (Fubini number): $1, 3, 13, 75, 541, \ldots$ for $n = 1, 2, 3, 4, 5$. The jump happens because each composition now spawns $\binom{n}{a_1, \ldots, a_k}$ arrangements. Worth computing both to see exactly where the factor of order enters.
- How many full sequences (non-decreasing) use exactly $k$ distinct values? That's the number of compositions of $n$ into exactly $k$ parts, $\binom{n-1}{k-1}$ — and summing over $k$ recovers $2^{n-1}$.
