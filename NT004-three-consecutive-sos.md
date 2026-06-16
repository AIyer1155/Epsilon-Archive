# Three Consecutive Sums of Two Squares

**Category:** Number Theory  
**Difficulty:** P2  
**Source:** Putnam 2000 A2  
**Tags:** `sum-of-two-squares` `brahmagupta-identity` `bootstrap`

---

## Problem

Prove that there exist infinitely many integers $n$ such that $n$, $n+1$, and $n+2$ are each the sum of the squares of two integers.

(Example: $0 = 0^2 + 0^2$, $1 = 0^2 + 1^2$, $2 = 1^2 + 1^2$.)

---

## The Trap

> Hunting for a formula in $k$, some family like $n = (2k)^2$, and hoping all three of $n, n+1, n+2$ come out as sums of two squares. The first two cooperate: $(2k)^2 = (2k)^2 + 0^2$ and $(2k)^2 + 1 = (2k)^2 + 1^2$. But $n+2 = 4k^2 + 2$ fails for most $k$, and you're left patching a family that doesn't hold.

---

## Key Insight

> Don't look for a formula, bootstrap. Sums of two squares are closed under multiplication, so one good triple gives you a bigger one. If $m-1$, $m$, $m+1$ are all sums of two squares, then so are $m^2-1$, $m^2$, $m^2+1$:
> - $m^2 - 1 = (m-1)(m+1)$, a product of two sums of two squares, so a sum of two squares;
> - $m^2 = m^2 + 0^2$;
> - $m^2 + 1 = m^2 + 1^2$.

---

## Solution

The closure fact: the identity

$$(a^2 + b^2)(c^2 + d^2) = (ac - bd)^2 + (ad + bc)^2$$

shows that a product of two sums of two squares is again a sum of two squares.

Call an integer $m \ge 1$ a *center* if $m-1$, $m$, and $m+1$ are all sums of two squares. The claim is:

$$m \text{ is a center} \;\Longrightarrow\; m^2 \text{ is a center.}$$

Set $M = m^2$ and check its three consecutive values:

- $M - 1 = m^2 - 1 = (m-1)(m+1)$. Both factors are sums of two squares, so by the closure fact $M-1$ is too.
- $M = m^2 = m^2 + 0^2$.
- $M + 1 = m^2 + 1^2$.

So $M = m^2$ is a center.

Now seed and iterate. Start from $m_0 = 9$: indeed $8 = 2^2 + 2^2$, $9 = 0^2 + 3^2$, $10 = 1^2 + 3^2$, so 9 is a center. Iterating $m_{k+1} = m_k^2$ gives

$$9 \;\to\; 81 \;\to\; 6561 \;\to\; \cdots,$$

each strictly larger than the last and each a center. Setting $n = m_k - 1$ gives infinitely many $n$ with $n, n+1, n+2$ all sums of two squares.

---

## What This Trains

When a problem asks for infinitely many objects, you don't need a closed form. You need a way to turn one solution into a bigger one. The whole proof rests on a single repeating step: center implies bigger center. This "one gives another" structure is how most existence-of-infinitely-many proofs actually work, and it saves you from the dead end of searching for a single formula that covers every case.

Closure identities are tools, not trivia. The Brahmagupta-Fibonacci identity (sums of two squares multiply to sums of two squares) is exactly what lets $m^2 - 1 = (m-1)(m+1)$ inherit the property. Knowing which sets are closed under which operations is what makes the bootstrap step legal.

---

## Variations

- Can you get four consecutive sums of two squares, $n, n+1, n+2, n+3$? No. Among any four consecutive integers one is $\equiv 3 \pmod 4$, and no number $\equiv 3 \pmod 4$ is a sum of two squares.
- Which single integers are sums of two squares? Exactly those whose prime factors $\equiv 3 \pmod 4$ all appear to an even power. That characterization is what sits underneath this whole problem.
