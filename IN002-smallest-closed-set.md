# The Smallest Closed Set

**Category:** Invariants  
**Difficulty:** P2  
**Source:** Putnam 2017 A1  
**Tags:** `closure` `invariant` `modular-arithmetic`

---

## Problem

Let $S$ be the smallest set of positive integers such that

- **(a)** $2 \in S$,
- **(b)** if $n^2 \in S$, then $n \in S$,
- **(c)** if $n \in S$, then $(n+5)^2 \in S$.

(Smallest means $S$ is contained in any other set satisfying (a) to (c).)

Which positive integers are **not** in $S$?

---

## The Trap

> The two squaring rules pull in opposite directions, so you start generating elements by hand: $2 \to 49 \to 7 \to \dots$, building a tree and hoping a pattern shows up. It won't, quickly. The rules are stated in terms of squares, so you assume the answer is about squares. It isn't.

---

## Key Insight

> Compose the two rules. Rule (c) puts $(n+5)^2$ in $S$, and rule (b) pulls $n+5$ back out of it. The net effect is $n \in S \Rightarrow n+5 \in S$. The squares were a distraction. The real rule is "add 5," which means the problem lives mod 5. Squaring and taking square roots never turn a nonzero residue mod 5 into zero, so multiples of 5 are unreachable.

---

## Solution

There are two things to show: that certain numbers are excluded, and that everything else is included.

**What's excluded.** Work mod 5. Squaring sends residues $0, 1, 2, 3, 4$ to $0, 1, 4, 4, 1$. A nonzero residue never squares to 0, and 0 never appears as the square of a nonzero residue. Rule (b) reverses a squaring, so it can't turn a nonzero residue into 0 either. Rule (c) adds 5 (no change mod 5) and then squares. The seed is $2 \not\equiv 0$.

So no rule ever produces a multiple of 5 from a non-multiple, and the seed isn't a multiple of 5. No multiple of 5 is in $S$.

Also $1 \notin S$. The only way to get 1 would be from $1^2 = 1$ through rule (b), which is circular and produces nothing new. It's never the seed, and rule (c) only outputs squares that are at least 49.

**What's included.** From $2 \in S$ and the composed rule $n \mapsto n+5$, every number $\equiv 2 \pmod 5$ is in $S$:

$$2, 7, 12, 17, 22, \ldots$$

To reach the other nonzero residues you have to lower numbers with rule (b), then climb again with $+5$. From any $n \in S$, rule (c) builds the square $(n+5)^2$, and rule (b) lets you take square roots of squares you've already placed. The square roots of the large squares already in $S$ cover every nonzero residue mod 5, while 0 stays unreachable. Once a single representative of each nonzero class is in $S$ above the relevant size, the $+5$ rule fills out every large enough non-multiple of 5, and checking the small cases ($2, 3, 4, 6, 7, \dots$) confirms they're all present.

The only permanent holdouts are the ones the invariant forbids: 1 and the multiples of 5.

---

## What This Trains

Compose your operations before you compute. The squares made this look like a hard problem about perfect squares. Composing (b) and (c) collapsed it to "add 5," and the whole thing became a question about residues mod 5. When a problem gives you two operations that look like inverses, check what their composition does first.

The two halves use opposite techniques. Showing something is in a generated set means finding a path to it. Showing something is out means finding a quantity no rule can change. Here that quantity is the residue mod 5. Knowing which half needs an invariant is the skill.

---

## Variations

- Replace the $+5$ in rule (c) with $+k$. The excluded set becomes 1 and the multiples of $k$, as long as the seed is coprime to $k$.
- What if the seed were 5 instead of 2? Then the invariant flips and almost everything is excluded.
