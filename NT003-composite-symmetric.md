# Composites and a Symmetric Form

**Category:** Number Theory
**Difficulty:** P1
**Source:** Putnam 1988 B1
**Tags:** `algebraic-identity` `factoring` `construction` `putnam`

---

## Problem

A composite positive integer is a product $ab$ with $a, b$ both in $\{2, 3, 4, \ldots\}$ (not necessarily distinct). Show that every composite integer can be written as

$$xy + xz + yz + 1$$

for some positive integers $x, y, z$.

---

## The Trap

> The expression $xy + xz + yz$ is the symmetric thing that shows up when you expand a product of three terms, so people reach for $(x+1)(y+1)(z+1)$ or chase a three-variable identity. That's one variable too many — you're handed a *two*-factor composite $ab$, and trying to match it against a fully symmetric three-variable form invites a mess. The "$+1$" also looks like noise until you see what it's compensating for.

---

## Key Insight

> You get to choose $x, y, z$ — so collapse the problem. Set $z = 1$. The target $xy + xz + yz + 1$ becomes $xy + x + y + 1$, which factors as $(x+1)(y+1)$. Now matching $ab$ is trivial: take $x = a-1$, $y = b-1$.

---

## Solution

Let the composite be $n = ab$ with $a, b \ge 2$. Choose

$$x = a - 1, \qquad y = b - 1, \qquad z = 1.$$

These are positive integers, since $a, b \ge 2$ gives $x, y \ge 1$. Now compute:

$$
xy + xz + yz + 1 = (a-1)(b-1) + (a-1)\cdot 1 + (b-1)\cdot 1 + 1.
$$

Expand:

$$
= \big(ab - a - b + 1\big) + (a - 1) + (b - 1) + 1 = ab.
$$

The $-a$ and $-b$ cancel against the $+a$ and $+b$, and the constants $+1 - 1 - 1 + 1$ cancel too, leaving exactly $ab = n$.

$$\boxed{\text{Every composite } n = ab \text{ equals } xy+xz+yz+1 \text{ with } x=a-1,\ y=b-1,\ z=1.}$$

---

## What This Trains

**Extra freedom is a gift — spend it to simplify.** The problem asks for *some* $x, y, z$, not all of them. Fixing $z = 1$ throws away nothing you needed and turns a symmetric three-variable expression into a clean factorization $(x+1)(y+1)$. When you have more variables than constraints, specializing the spares is often the whole solution.

It also trains **recognizing a factorization in disguise.** $xy + x + y + 1 = (x+1)(y+1)$ is the same shift-and-factor move behind Simon's Favorite Factoring Trick; spotting that the "$+1$" is exactly the constant that completes the product is what makes the construction obvious rather than lucky.

---

## Variations

- Why does the problem specify *composite*? A prime $p$ has no factorization $ab$ with $a, b \ge 2$, so this construction has nothing to latch onto — and indeed primes generally can't be written in this form with positive $x, y, z$.
- Can you write $n$ in this form in more than one way? Different factorizations $ab$ of $n$ give different triples — so the number of representations grows with the number of factor pairs.
