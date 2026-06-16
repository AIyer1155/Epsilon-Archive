# Composites and a Symmetric Form

**Category:** Number Theory  
**Difficulty:** P1  
**Source:** Putnam 1988 B1  
**Tags:** `algebraic-identity` `factoring` `construction`

---

## Problem

A composite positive integer is a product $ab$ with $a, b$ both in $\{2, 3, 4, \ldots\}$ (not necessarily distinct). Show that every composite integer can be written as

$$xy + xz + yz + 1$$

for some positive integers $x, y, z$.

---

## The Trap

> The expression $xy + xz + yz$ is symmetric in three variables, so you reach for $(x+1)(y+1)(z+1)$ or some three-variable identity. That's one variable too many. You're handed a two-factor product $ab$, and matching it against a fully symmetric three-variable form gets messy fast.

---

## Key Insight

> You get to pick $x, y, z$, so set $z = 1$. The target becomes $xy + x + y + 1$, which factors as $(x+1)(y+1)$. Now matching $ab$ is easy: take $x = a-1$, $y = b-1$.

---

## Solution

Let the composite be $n = ab$ with $a, b \ge 2$. Choose

$$x = a - 1, \qquad y = b - 1, \qquad z = 1.$$

These are positive integers, since $a, b \ge 2$ gives $x, y \ge 1$. Now compute:

$$xy + xz + yz + 1 = (a-1)(b-1) + (a-1) + (b-1) + 1.$$

Expanding:

$$= (ab - a - b + 1) + (a - 1) + (b - 1) + 1 = ab.$$

The $-a$ and $-b$ cancel against the $+a$ and $+b$, the constants $+1 - 1 - 1 + 1$ cancel, and you're left with $ab = n$.

---

## What This Trains

When a problem asks for some $x, y, z$ rather than all of them, the extra freedom is there to be spent. Fixing $z = 1$ throws away nothing you needed and collapses a symmetric three-variable expression into a clean factorization $(x+1)(y+1)$. When you have more variables than constraints, specializing the spare ones is often the whole solution.

It also trains spotting a hidden factorization. $xy + x + y + 1 = (x+1)(y+1)$ is the same shift-and-factor move behind Simon's Favorite Factoring Trick. The "+1" is exactly the constant that completes the product.

---

## Variations

- Why does the problem need $n$ to be composite? A prime has no factorization $ab$ with $a, b \ge 2$, so the construction has nothing to work with.
- Can you write $n$ in this form in more than one way? Different factorizations $ab$ give different triples, so the number of representations grows with the number of factor pairs.
