---
type: exercise
status: in-progress
created: 2026-09-18
course: IE-616
semester: 2026-HWS
tags: [apriori]
due: 2026-09-25
---

# Exercise 02 — Apriori by hand

**Task:** Given the toy transaction DB below, mine all frequent itemsets with $\text{supp} \ge 0.4$ and all rules with $\text{conf} \ge 0.6$.

## Transactions
| TID | Items |
|-----|-------|
| T1  | {A, B, C} |
| T2  | {A, C} |
| T3  | {A, B, D} |
| T4  | {B, C} |
| T5  | {A, C, D} |

## Work

- $|D| = 5$, min-support count $= \lceil 0.4 \cdot 5 \rceil = 2$.
- $L_1$: A(4), B(3), C(4), D(2)   → all pass.
- $C_2$ = {AB, AC, AD, BC, BD, CD}. Support counts: AB(2), AC(3), AD(2), BC(2), BD(1), CD(1). → $L_2$ = {AB, AC, AD, BC}.
- $C_3$: join $L_2$ → {ABC, ABD, ACD}. Prune ABD (BD not in $L_2$). Counts: ABC(1), ACD(1). → $L_3 = \emptyset$. Stop.

**Frequent itemsets:** A, B, C, D, AB, AC, AD, BC.

**Rules (conf ≥ 0.6):**
- $A \Rightarrow C$: 3/4 = 0.75 ✓
- $C \Rightarrow A$: 3/4 = 0.75 ✓
- $A \Rightarrow B$: 2/4 = 0.5 ✗
- $B \Rightarrow A$: 2/3 ≈ 0.67 ✓
- $B \Rightarrow C$: 2/3 ≈ 0.67 ✓
- $D \Rightarrow A$: 2/2 = 1.0 ✓  (but small sample!)

## Reflection
- [x] Reproduced the monotonicity pruning (ABD via BD).
- [ ] Ask in tutorial: how do we handle the D-rule confidence of 1.0 with only 2 supporting transactions?
