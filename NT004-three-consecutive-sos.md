# Three Consecutive Sums of Two Squares

**Category:** Number Theory
**Difficulty:** P2
**Source:** Putnam 2000 A2
**Tags:** `sum-of-two-squares` `brahmagupta-identity` `bootstrap` `putnam`

---

## Problem

Prove that there exist infinitely many integers $n$ such that $n$, $n+1$, and $n+2$ are each the sum of the squares of two integers.

*(Example: $0 = 0^2 + 0^2$, $\;1 = 0^2 + 1^2$, $\;2 = 1^2 + 1^2$.)*

---

## The Trap

> The obvious move is to hunt for a formula in $k$ — some family like $n = (2k)^2$ — and hope all three of $n, n+1, n+2$ come out as sums of two squares. The first two cooperate: $(2k)^2 = (2k)^2 + 0^2$ and $(2k)^2 + 1 = (2k)^2 + 1^2$. But $n+2 = 4k^2 + 2$ refuses to fit for most $k$, and you're left patching a family that doesn't hold. Searching for a single closed form is the wrong shape of attack.

---

## Key Insight

> Don't search for a formula — **bootstrap**. Sums of two squares are closed under multiplication (the Brahmagupta–Fibonacci identity), so if you already have one good triple, you can manufacture a strictly larger one. Given a "middle" $m$ where $m-1$, $m$, $m+1$ are all sums of two squares, the number $m^2$ is a new such middle:
> - $m^2 - 1 = (m-1)(m+1)$ — a product of two sums of two squares, hence a sum of two squares;
> - $m^2 = m^2 + 0^2$;
> - $m^2 + 1 = m^2 + 1^2$.
>
> One good triple breeds a bigger one, forever.

---

## Solution

**The closure fact.** The identity
$$(a^2 + b^2)(c^2 + d^2) = (ac - bd)^2 + (ad + bc)^2$$
shows that a product of two sums of two squares is again a sum of two squares.

**The construction.** Call an integer $m \ge 1$ a *center* if $m-1$, $m$, and $m+1$ are all sums of two squares. We claim:

$$m \text{ is a center} \;\Longrightarrow\; m^2 \text{ is a center.}$$

Set $M = m^2$ and check its three consecutive values:

- $M - 1 = m^2 - 1 = (m-1)(m+1)$. Since $m$ is a center, both $m-1$ and $m+1$ are sums of two squares, so by the closure fact their product $M - 1$ is too.
- $M = m^2 = m^2 + 0^2$. Always a sum of two squares.
- $M + 1 = m^2 + 1^2$. Always a sum of two squares.

So $M = m^2$ is a center.

**Seeding and iterating.** Start from the center $m_0 = 5$: indeed $4 = 2^2 + 0^2$, $5 = 1^2 + 2^2$, $6 = ?$ — wait, $6$ is *not* a sum of two squares, so $5$ is not a center. Use instead $m_0 = 2$: $1 = 0^2+1^2$, $2 = 1^2+1^2$, $3$ is not a sum of two squares either. The clean seed is $m_0 = 1$: $0 = 0^2+0^2$, $1 = 0^2+1^2$, $2 = 1^2+1^2$ — all three are sums of two squares, so $1$ is a center.

Now iterate $m_{k+1} = m_k^2$. From $m_0 = 1$ this stays at $1$ (a fixed point), so instead take the next genuine center to start the climb: $m_0 = 9$ works ($8 = 2^2+2^2$, $9 = 0^2+3^2$, $10 = 1^2+3^2$). Then
$$9 \;\to\; 81 \;\to\; 6561 \;\to\; \cdots,$$
each $m_{k+1} = m_k^2$ strictly larger than the last and provably a center. Setting $n = m_k - 1$ for each $k$ gives infinitely many $n$ with $n, n+1, n+2$ all sums of two squares.

$$\boxed{\text{Infinitely many such } n \text{ exist; e.g. } n = m_k - 1 \text{ where } m_0 = 9,\ m_{k+1} = m_k^2.}$$

---

## What This Trains

**Bootstrapping beats formula-hunting.** When a problem asks for *infinitely many* objects, you don't need a closed form — you need a way to turn one solution into a bigger one. The whole proof rests on a single self-reproducing step: center $\Rightarrow$ bigger center. This "one breeds another" structure is how most existence-of-infinitely-many proofs actually work, and recognizing it saves you from the dead-end search for a magic family.

**Closure identities are tools, not trivia.** The Brahmagupta–Fibonacci identity (sums of two squares multiply to sums of two squares) is exactly what lets $m^2 - 1 = (m-1)(m+1)$ inherit the property. Knowing which sets are closed under which operations — sums of two squares under multiplication, here — is what makes the bootstrap step legal.

---

## Variations

- Can you get *four* consecutive sums of two squares, $n, n+1, n+2, n+3$? (No — among any four consecutive integers one is $\equiv 3 \pmod 4$, and no number $\equiv 3 \pmod 4$ is a sum of two squares.)
- Which single integers are sums of two squares? (Exactly those whose primes $\equiv 3 \pmod 4$ all appear to an even power — the classical characterization underlying this whole problem.)
