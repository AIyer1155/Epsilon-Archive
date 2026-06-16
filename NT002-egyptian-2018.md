# Splitting 3/2018

**Category:** Number Theory
**Difficulty:** P1
**Source:** Putnam 2018 A1
**Tags:** `diophantine` `factoring` `simon-trick` `putnam`

---

## Problem

Find all ordered pairs $(a, b)$ of positive integers satisfying

$$\frac{1}{a} + \frac{1}{b} = \frac{3}{2018}.$$

---

## The Trap

> Clearing denominators gives $2018(a+b) = 3ab$, and then it's tempting to start guessing — fix $a$, solve for $b$, check when it's an integer, grind through cases. You'll find a few solutions and never be sure you have them all. The equation looks like it resists factoring because of that stray $3ab$ on one side.

---

## Key Insight

> An equation of the form (linear) $=$ (product) wants to be turned into (product) $=$ (constant). Multiply through to isolate $ab$, then complete the rectangle — add the right constant to both sides so the left factors. Once it reads $(\,\cdot\,)(\,\cdot\,) = N$, finding all solutions is just listing divisors of $N$.

---

## Solution

Start from $2018(a+b) = 3ab$. To factor, multiply both sides by $3$ so the $ab$ term has a clean square coefficient:

$$9ab - 3 \cdot 2018(a+b) = 0.$$

Now add $2018^2$ to both sides to complete the factorization (this is Simon's Favorite Factoring Trick):

$$9ab - 6054a - 6054b + 2018^2 = 2018^2.$$

The left side factors:

$$(3a - 2018)(3b - 2018) = 2018^2.$$

Let $u = 3a - 2018$ and $v = 3b - 2018$, so $uv = 2018^2$. Since $a, b$ are positive integers, $u$ and $v$ are integers, and $uv > 0$ forces both positive (if both were negative, $a < 673$ and $b < 673$ would make $1/a + 1/b$ far larger than $3/2018$). So we need positive divisor pairs of

$$2018^2 = 2^2 \cdot 1009^2.$$

**The divisibility constraint.** Not every divisor works: we need $a = (u + 2018)/3$ to be an integer, i.e. $u \equiv -2018 \equiv 1 \pmod 3$. Among the divisors of $2018^2$, which are $\equiv 1 \pmod 3$?

Since $2 \equiv 2$ and $1009 \equiv 1 \pmod 3$, a divisor $2^i \cdot 1009^j$ (with $0 \le i \le 2$, $0 \le j \le 2$) is $\equiv 2^i \pmod 3$. That's $\equiv 1$ exactly when $i$ is even, i.e. $i \in \{0, 2\}$. So the valid $u$ are

$$1,\quad 4,\quad 1009,\quad 4 \cdot 1009,\quad 1009^2,\quad 4 \cdot 1009^2,$$

six values. Each determines $v = 2018^2 / u$ (automatically also $\equiv 1 \pmod 3$, since $uv \equiv 1$ and $u \equiv 1$), and hence one ordered pair $(a, b)$. Working them out:

$$(673,\ 673 \cdot 2018),\quad (674,\ 337 \cdot 1009),\quad (1009,\ 2018)$$

together with their three reverses.

$$\boxed{\text{There are } 6 \text{ ordered pairs.}}$$

---

## What This Trains

**Simon's Favorite Factoring Trick** — when an equation mixes a product term $xy$ with linear terms $x$ and $y$, you can almost always add a constant to force it into $(x + c)(y + d) = N$. From there the problem becomes divisor-counting, which is finite and exhaustive. This converts "guess and check forever" into "list the divisors," and it's one of the highest-frequency moves in competition number theory.

The second half trains a habit that catches people out: **a factorization gives candidate solutions, not final ones.** You still have to check the integrality/sign constraints. Here the $\pmod 3$ filter cuts nine divisor pairs down to six — skip it and you overcount.

---

## Variations

- Replace $2018$ with a prime $p$: how does the count change? (The exponent structure of $p^2$ changes which divisors survive the mod-3 filter.)
- For $\frac{1}{a} + \frac{1}{b} = \frac{1}{N}$, the count of ordered pairs is the number of divisors of $N^2$ — clean because there's no awkward numerator forcing a congruence filter.
