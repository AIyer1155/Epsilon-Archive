# The Monty Hall Problem

**Category:** Conditional Probability  
**Difficulty:** P1  
**Source:** Parade Magazine, 1990 / classical  
**Tags:** `bayes` `conditioning` `sample-space`

---

## Problem

Three doors. One hides a car, two hide goats. You pick door 1. The host who knows what's behind every door opens door 3 to reveal a goat. Should you switch to door 2?

---

## The Trap

> "Two doors left, so it's 50/50." This ignores that the host's action carries information. He never opens the car door, so his choice is not random.

---

## Key Insight

> Your initial pick is wrong with probability $\frac{2}{3}$. When it's wrong, the host is forced to open the one remaining goat door which leaves the car behind the other one. So switching wins exactly when your initial pick was wrong, which is $\frac{2}{3}$ of the time.

---

## Solution

**By cases:**

- You picked the car (prob $\frac{1}{3}$): host opens either goat door. Switching loses.
- You picked goat 1 (prob $\frac{1}{3}$): host must open the door with goat 2. Switching wins.
- You picked goat 2 (prob $\frac{1}{3}$): host must open the door with goat 1. Switching wins.

$$P(\text{win by switching}) = \frac{2}{3}, \quad P(\text{win by staying}) = \frac{1}{3}$$

**Always switch.**

---

## What This Trains

The host's constraint is the whole problem. When an agent with information takes an action, that action updates your probabilities, even if the action looks neutral. This reasoning pattern appears constantly in market microstructure: what does the fact that someone is willing to trade with you* tell you?

---

## Variations

- 100 doors, you pick one, host opens 98 goat doors. Switch?
- What if the host opens a door at random (and happened to reveal a goat)? Does the answer change?

