# Full Sequences

**Category:** Combinatorics  
**Difficulty:** P2  
**Source:** Classic combinatorics  
**Tags:** `bijection` `compositions` `binary-strings`

---

## Problem

A non-decreasing sequence of $n$ positive integers is called **full** if, for each integer $k \ge 2$ that appears in the sequence, the number $k-1$ also appears.

Find the number of full sequences of length $n$.

---

## The Trap

> Counting by casework: fix the maximum value $k$, then count how to place values $1$ through $k$ so each appears at least once. This runs straight into Stirling numbers and a sum you don't want to evaluate. You're counting the right object the hard way.

---

## Key Insight

> A non-decreasing full sequence is determined by how many times each value appears. Those counts $(a_1, \ldots, a_k)$, each at least 1 and summing to $n$, are exactly a composition of $n$. Compositions of $n$ are counted by the $n-1$ gaps between $n$ items, each a cut or not, giving $2^{n-1}$.

---

## Solution

The sequence is non-decreasing, so the multiset of values determines it completely. Just sort them. So counting full sequences means counting valid multisets.

Now unpack "full." If the largest value used is $k$, fullness forces every one of $1, 2, \ldots, k$ to appear at least once, since a missing value below $k$ would orphan the value above it. So the values used are exactly $\{1, 2, \ldots, k\}$.

Let $a_i \ge 1$ be the number of times value $i$ appears, for $i = 1, \ldots, k$. Then

$$a_1 + a_2 + \cdots + a_k = n, \qquad a_i \ge 1.$$

This is a composition of $n$: an ordered tuple of positive integers summing to $n$. The map is a bijection. A full sequence gives its count vector, and a composition $(a_1, \ldots, a_k)$ rebuilds the unique sorted sequence by writing value $i$ exactly $a_i$ times.

To count compositions, line up $n$ units with $n-1$ gaps between them:

$$1 \;\square\; 1 \;\square\; 1 \;\square\; \cdots \;\square\; 1.$$

A composition corresponds to choosing which gaps are cuts. Each of the $n-1$ gaps is independently a cut or not, so there are $2^{n-1}$ compositions, hence $2^{n-1}$ full sequences.

For a quick check: $n=3$ gives $[1,1,1], [1,1,2], [1,2,2], [1,2,3]$, four sequences, and $2^2 = 4$.

---

## What This Trains

Bijection thinking. When a direct count produces a messy sum, ask what simpler object you're actually counting. Recognizing the count vector of a non-decreasing sequence as a composition of $n$ collapses the problem to a known $2^{n-1}$.

The gaps model for compositions is worth keeping on hand: compositions of $n$ into positive parts correspond to subsets of the $n-1$ internal gaps, which correspond to binary strings of length $n-1$, all counted by $2^{n-1}$.

---

## Variations

- Drop "non-decreasing." If the sequence can be in any order, the count is no longer $2^{n-1}$. It's the ordered Bell number: $1, 3, 13, 75, 541, \ldots$ for $n = 1, 2, 3, 4, 5$. Each composition now spawns $\binom{n}{a_1, \ldots, a_k}$ arrangements, which is where the jump comes from.
- How many non-decreasing full sequences use exactly $k$ distinct values? That's the number of compositions of $n$ into exactly $k$ parts, $\binom{n-1}{k-1}$. Summing over $k$ recovers $2^{n-1}$.
