# Splitting 3/2018

**Category:** Number Theory  
**Difficulty:** P1  
**Source:** Putnam 2018 A1  
**Tags:** `diophantine` `factoring` `simon-trick`

---

## Problem

Find all ordered pairs $(a, b)$ of positive integers satisfying

$$\frac{1}{a} + \frac{1}{b} = \frac{3}{2018}.$$

---

## The Trap

> Clearing denominators gives $2018(a+b) = 3ab$, and then you start fixing $a$, solving for $b$, and checking when it's an integer. You'll find a few solutions and never be sure you have all of them.

---

## Key Insight

> An equation with a product term and linear terms wants to be factored. Isolate the $ab$ term, add the right constant to both sides, and the left side splits into a product equal to a constant. Then you just list divisors.

---

## Solution

Start from $2018(a+b) = 3ab$. Multiply by 3 so the $ab$ term has a square coefficient:

$$9ab - 3 \cdot 2018(a+b) = 0.$$

Add $2018^2$ to both sides. This is Simon's Favorite Factoring Trick:

$$9ab - 6054a - 6054b + 2018^2 = 2018^2.$$

The left side factors:

$$(3a - 2018)(3b - 2018) = 2018^2.$$

Let $u = 3a - 2018$ and $v = 3b - 2018$, so $uv = 2018^2$. Since $a, b$ are positive integers, $u$ and $v$ are integers with $uv > 0$. Both must be positive: if both were negative we'd need $a < 673$ and $b < 673$, which makes $\frac{1}{a} + \frac{1}{b}$ far larger than $\frac{3}{2018}$. So we want positive divisor pairs of

$$2018^2 = 2^2 \cdot 1009^2.$$

Not every divisor works. We need $a = (u + 2018)/3$ to be an integer, so $u \equiv -2018 \equiv 1 \pmod 3$. A divisor $2^i \cdot 1009^j$ is $\equiv 2^i \pmod 3$ (since $1009 \equiv 1$), which is $\equiv 1$ exactly when $i$ is even. So the valid values of $u$ are

$$1, \quad 4, \quad 1009, \quad 4 \cdot 1009, \quad 1009^2, \quad 4 \cdot 1009^2,$$

six of them. Each fixes $v = 2018^2 / u$ and gives one ordered pair $(a, b)$. Working them out:

$$(673,\ 673 \cdot 2018), \quad (674,\ 337 \cdot 1009), \quad (1009,\ 2018)$$

and their three reverses. There are 6 ordered pairs.

---

## What This Trains

Simon's Favorite Factoring Trick: when an equation mixes a product term $xy$ with linear terms in $x$ and $y$, add a constant to force it into $(x+c)(y+d) = N$. After that the problem is divisor counting, which is finite. This turns "guess and check forever" into "list the divisors."

The second half is the part people skip: a factorization gives you candidate solutions, not final ones. You still have to apply the integrality constraint. Here the mod 3 filter cuts nine divisor pairs down to six.

---

## Variations

- Replace 2018 with a prime $p$. How does the count change?
- For $\frac{1}{a} + \frac{1}{b} = \frac{1}{N}$, the number of ordered pairs is the number of divisors of $N^2$, with no congruence filter to worry about.
