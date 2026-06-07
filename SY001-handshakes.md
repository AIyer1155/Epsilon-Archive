# The Handshakes

**Category:** Symmetry  
**Difficulty:** P1  
**Source:** Classic combinatorics  
**Tags:** `counting` `symmetry` `combinations`

---

## Problem

Ten people at a party. Each shakes hands with every other person exactly once. How many handshakes?

---

## The Trap

> Multiplying $10 \times 9 = 90$ and forgetting you've counted each handshake twice — once for each participant.

---

## Key Insight

> A handshake is an unordered pair. Choosing 2 people from 10 gives $\binom{10}{2}$ directly.

---

## Solution

Each handshake is a unique pair of people. The number of ways to choose 2 from 10:

$$\binom{10}{2} = \frac{10 \times 9}{2} = 45$$

Or: $10 \times 9 = 90$ ordered pairs, divide by 2 since each handshake is counted twice. Same answer.

$$\boxed{45}$$

---

## What This Trains

Ordered vs unordered counting. Any time you're counting pairs, connections, or matches, ask: does order matter? If not, divide by the overcounting factor. This is the foundation of most combinatorics problems.

---

## Variations

- $n$ people at a party — general formula?
- A round-robin tournament with 10 teams. How many games are played?
- Each person shakes hands with everyone *except* the person directly across from them at a circular table. How many handshakes now?

