# The Envelope Problem

**Category:** Expected Value  
**Difficulty:** P2  
**Source:** Classic decision theory  
**Tags:** `expected-value` `paradox` `conditional-expectation`

---

## Problem

Two envelopes each contain money. One has twice as much as the other. You pick one, open it, see \$100. Should you switch? The other envelope contains either \$50 or \$200 with equal probability, so the expected value of switching is $\frac{1}{2}(50) + \frac{1}{2}(200) = \$125 > \$100$. But by symmetry, the same argument applies before you open the envelope. So should you always switch, even without looking?

---

## The Trap

> Taking the $\frac{1}{2}(50) + \frac{1}{2}(200)$ calculation at face value. The error is treating both cases as equally likely after conditioning on seeing \$100 which requires a prior over how the amounts were chosen.

---

## Key Insight

> The two events ("other envelope has \$50" and "other envelope has \$200") are not automatically equally likely given you see \$100. Their relative probability depends on how the envelopes were filled. Without specifying a prior, the expected value calculation is undefined.

---

## Solution

Let the two amounts be $m$ and $2m$ for some $m > 0$.

You see \$100. This means either:
- $m = 100$ and the other has \$200, or
- $2m = 100 \Rightarrow m = 50$ and the other has \$50.

Let $p$ = probability you're in the first case. Then:

$$E[\text{other envelope}] = p \cdot 200 + (1-p) \cdot 50$$

This equals \$100 (indifferent to switching) when $p = \frac{1}{3}$, favors switching when $p > \frac{1}{3}$, and favors staying when $p < \frac{1}{3}$.

The value of $p$ depends entirely on the prior distribution over $m$. Without it, the problem is ill-posed. The naive $p = \frac{1}{2}$ assumption smuggles in a specific (improper) prior.

**So should you switch?** If you have no information about how the envelopes were filled: it doesn't matter. The symmetry argument is correct. The same logic applies to whichever envelope you hold, so there's no edge in switching.

---

## What This Trains

Conditional expectation requires a well-defined probability model. When a calculation gives a paradoxical result, check whether the probabilities being used are actually justified. This is directly relevant to Bayesian reasoning and model specification in finance.

---

## Variations

- If you know the amounts are drawn uniformly from {\$10, \$20, \$40, \$80, \$160}, and you see \$40, should you switch?
- What prior over $m$ makes switching always optimal regardless of what you see?

