# The Medical Test

**Category:** Conditional Probability  
**Difficulty:** P1  
**Source:** Classic Bayes / Kahneman  
**Tags:** `bayes` `base-rate` `false-positive`

---

## Problem

A disease affects 1 in 1000 people. A test is 99% accurate. It correctly identifies 99% of sick people and correctly clears 99% of healthy people. You test positive. What is the probability you actually have the disease?

---

## The Trap

> Saying 99%. The test is 99% accurate, you tested positive, so you're 99% likely to be sick. This ignores the base rate entirely.

---

## Key Insight

> Most positive results are false positives because the disease is so rare that even a 1% error rate on healthy people buries the true positives.

---

## Solution

Out of 100,000 people:

- 100 have the disease. Test catches 99% → **99 true positives**.
- 99,900 are healthy. Test wrongly flags 1% → **999 false positives**.

Total positives: $99 + 999 = 1098$.

$$P(\text{sick} \mid \text{positive}) = \frac{99}{1098} \approx 9\%$$

You're more likely healthy than sick, even after a positive test.

**Via Bayes directly:**

$$P(\text{sick} \mid +) = \frac{P(+ \mid \text{sick}) \cdot P(\text{sick})}{P(+)} = \frac{0.99 \times 0.001}{0.99 \times 0.001 + 0.01 \times 0.999} \approx 0.09$$

---

## What This Trains

Base rate neglect is one of the most common probabilistic errors in medicine, in finance, and in interviews. Whenever someone gives you a conditional probability, ask: what's the prior? A signal that's 99% accurate on a rare event is mostly noise in practice.

---

## Variations

- How accurate would the test need to be to give 50% confidence after a positive result?
- If you test positive twice independently, what's the probability you're sick?

