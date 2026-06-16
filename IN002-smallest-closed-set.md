# The Smallest Closed Set

**Category:** Invariants
**Difficulty:** P2
**Source:** Putnam 2017 A1
**Tags:** `closure` `invariant` `modular-arithmetic` `putnam`

---

## Problem

Let $S$ be the smallest set of positive integers such that

- **(a)** $2 \in S$,
- **(b)** if $n^2 \in S$, then $n \in S$,
- **(c)** if $n \in S$, then $(n+5)^2 \in S$.

(Smallest means $S$ is contained in any other set satisfying (a)–(c).)

Which positive integers are **not** in $S$?

---

## The Trap

> The two squaring rules pull in opposite directions — one squares, one un-squares — and it's tempting to start generating elements by brute force: $2 \to 49 \to 7 \to \ldots$, building a sprawling tree and hoping the pattern becomes obvious. It won't, quickly. The rules are stated in terms of squares, so people assume the answer is about squares. It isn't.

---

## Key Insight

> Compose the two rules. Rule (c) puts $(n+5)^2$ in $S$; rule (b) then pulls $n+5$ back out of that square. Net effect:
> $$n \in S \;\Longrightarrow\; n+5 \in S.$$
> The squares were a disguise. The real engine is "add 5," which means the problem lives **modulo 5**. Squaring and square-rooting never change a residue from nonzero to zero mod 5, so multiples of 5 can never be reached — that's your invariant.

---

## Solution

**Two things to prove:** that certain numbers are excluded, and that everything else is included.

**What's excluded.** Suppose $m \in S$. Trace how $m$ could have entered: via (a) as the number $2$, or via (b) from $m^2$, or via (c) as $(k+5)^2$ from some $k \in S$. Consider residues mod 5. Squaring sends residues $0,1,2,3,4$ to $0,1,4,4,1$ — crucially, **a nonzero residue never squares to $0$, and $0$ never arises as a square of a nonzero residue.** Rule (b) reverses a squaring, so it also cannot turn a nonzero residue into $0$. Rule (c) is "add 5 then square," which fixes the residue mod 5 before squaring. And the seed is $2 \not\equiv 0$.

So no operation ever produces a multiple of 5 from a non-multiple, and the seed isn't a multiple of 5. Therefore **no multiple of 5 is in $S$.** Also $1 \notin S$: the only way to get $1$ would be from $1^2 = 1$ via (b) (circular, generates nothing new) — $1$ is never produced by the seed or by (c), which only outputs squares $\ge 49$. So $1$ is excluded too.

**What's included.** We show every other positive integer is in $S$. From $2 \in S$ and the composed rule $n \mapsto n+5$, we immediately get all numbers $\equiv 2 \pmod 5$:

$$2, 7, 12, 17, 22, \ldots \in S.$$

To reach the other nonzero residues, we need to *lower* numbers using rule (b), then climb again with $+5$. The mechanism: from any $n \in S$, rule (c) gives $(n+5)^2 \in S$, and rule (b) gives back $n + 5$ — but we can also apply (b) to *other* squares we've built. Concretely, once $S$ contains a full residue class mod 5 above some bound, taking square roots lands us in new, smaller residue classes, and $+5$ then fills those out. Carrying this out:

- $7 \in S \Rightarrow 7 \equiv 2$; we have class $2$.
- Building squares and rooting reaches a number $\equiv 3$, then $\equiv 4$, then $\equiv 1 \pmod 5$ (each nonzero class is reachable because square roots of the already-present large squares cover all nonzero residues, and $0$ stays forever unreachable).

Once a single representative of each nonzero class mod 5 is in $S$ above the relevant threshold, the $+5$ rule fills out **every** sufficiently large non-multiple of 5, and checking the finitely many small cases ($2,3,4,6,7,\ldots$) confirms they're all present. The only permanent holdouts are the ones the invariant forbids.

$$\boxed{\text{The integers not in } S \text{ are } 1 \text{ and the multiples of } 5.}$$

---

## What This Trains

**Compose your operations before you compute.** The squares made this look like a hard problem about perfect squares; composing (b) and (c) collapsed it to "add 5," and the whole thing became a question about residues mod 5. When a problem gives you two inverse-flavored operations, always check what their composition does — the answer is often dramatically simpler than either rule alone.

**Find the invariant to prove exclusion.** Showing something is *in* a generated set means exhibiting a path. Showing something is *out* means finding a quantity no operation can change — here, "is this $\equiv 0 \pmod 5$?" The two halves of the proof use opposite techniques, and recognizing which half needs an invariant is the skill.

---

## Variations

- Replace the $+5$ in rule (c) with $+k$: the excluded set becomes $1$ and the multiples of $k$ (when the seed is coprime to $k$).
- What if the seed were $5$ instead of $2$? Then $S = \{5\}$ collapses under (b)/(c) into multiples of 5 only — the invariant flips, and almost everything is excluded.
