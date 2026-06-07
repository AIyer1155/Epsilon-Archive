# The Light Switches

**Category:** Invariants  
**Difficulty:** P1  
**Source:** Classic / folklore  
**Tags:** `invariants` `number-theory` `divisors`

---

## Problem

100 switches, all off. 100 people walk through one at a time. Person $k$ toggles every switch that is a multiple of $k$. Which switches are on after all 100 people have walked through?

---

## The Trap

> Trying to simulate it. Switch $n$ gets toggled once for each divisor of $n$ — so the question reduces to: which numbers have an odd number of divisors?

---

## Key Insight

> Divisors come in pairs: if $d$ divides $n$, so does $\frac{n}{d}$. The only exception is when $d = \frac{n}{d}$, i.e. $d = \sqrt{n}$ — which happens exactly when $n$ is a perfect square. So only perfect squares end up toggled an odd number of times.

---

## Solution

Switch $n$ is toggled by person $k$ if and only if $k$ divides $n$. So switch $n$ is toggled exactly $\tau(n)$ times, where $\tau(n)$ is the number of divisors of $n$.

A switch ends up ON iff it was toggled an odd number of times, i.e. iff $\tau(n)$ is odd.

Divisors pair up as $(d, n/d)$. These are distinct unless $d = \sqrt{n}$, which requires $n$ to be a perfect square.

So $\tau(n)$ is odd $\iff$ $n$ is a perfect square.

The perfect squares from 1 to 100: $1, 4, 9, 16, 25, 36, 49, 64, 81, 100$.

**10 switches are on.**

---

## What This Trains

Invariant / structural thinking: instead of tracking the process, find the property that determines the outcome. Divisors pairing up is a classic parity argument. Once you see it, the simulation becomes unnecessary.

---

## Variations

- 1000 switches, 1000 people. How many are on?
- Person $k$ toggles switches that are *multiples of $k$, but only if $k$ is prime*. Which switches are on now?

