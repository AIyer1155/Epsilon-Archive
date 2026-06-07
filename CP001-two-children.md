# The Two Children Problem

**Category:** Conditional Probability  
**Difficulty:** P2  
**Source:** Classic / Martin Gardner  
**Tags:** `bayes` `sample-space` `conditioning`

---

## Problem

A family has two children. You learn that at least one is a boy. What's the probability both are boys?

Harder version: at least one is a boy born on a Tuesday. Now what?

---

## The Trap

> For part one: most people say $\frac{1}{2}$ because "the other child is independently a boy or girl." But conditioning shrinks the sample space — GG is gone.

> For part two: the Tuesday detail feels like it shouldn't matter. It does, and the answer is weird.

---

## Key Insight

> Always list the full sample space, then cross off what the condition eliminates. Don't reason about "the other child" in isolation — there is no "other child" until you've fixed the sample space.

---

## Solution

**Part 1:**

Equally likely outcomes: BB, BG, GB, GG. Conditioning on "at least one boy" removes GG.

$$P(\text{both boys}) = \frac{1}{3}$$

**Part 2:**

Each child has 14 equally likely types (boy/girl × 7 days). Two children → $14^2 = 196$ total outcomes.

Outcomes with at least one "boy born Tuesday" (BTu): $14 + 14 - 1 = 27$.

Outcomes where both are boys AND at least one is BTu: $7 + 7 - 1 = 13$.

$$P(\text{both boys} \mid \text{at least one BTu boy}) = \frac{13}{27} \approx 0.48$$

The more specific the condition, the closer you get to $\frac{1}{2}$. If you're told *which* child is a boy, you're exactly at $\frac{1}{2}$.

---

## What This Trains

Enumerate first, condition second. Never skip the sample space. The Tuesday variant is also a useful reminder that specificity shifts probability in ways that aren't obvious — this shows up in Bayesian reasoning constantly.

---

## Variations

- At least one boy born in January? (Answer: $\frac{23}{47}$.)
- What's the limiting probability as the conditioning event becomes arbitrarily rare?

