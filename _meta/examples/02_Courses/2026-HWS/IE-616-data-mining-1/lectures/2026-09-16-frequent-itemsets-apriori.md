---
type: lecture
status: in-progress
created: 2026-09-16
course: IE-616
semester: 2026-HWS
tags: [association-rules, apriori, frequent-itemsets]
moc: ["[[machine-learning]]"]
due: 
---

# Frequent itemsets & the Apriori algorithm

> [!question] Guiding questions
> - What is *support* and *confidence*, and why can't confidence be interpreted alone?
> - Why does the Apriori algorithm work — what is the monotonicity property?
> - Where does Apriori break down in practice, and what is FP-Growth's improvement?

> [!note] Notes
> - **Itemset** $I \subseteq \mathcal{I}$; **transaction** $T$ contains $I$ if $I \subseteq T$.
> - **Support**: $\text{supp}(I) = \frac{|\{T : I \subseteq T\}|}{|D|}$. Fraction of transactions containing $I$.
> - **Confidence** of rule $X \Rightarrow Y$: $\text{conf}(X \Rightarrow Y) = \frac{\text{supp}(X \cup Y)}{\text{supp}(X)}$.
> - **Apriori monotonicity:** if $I$ is frequent, all subsets of $I$ are frequent → prune early.
> - **Algorithm:** generate $L_1$ (frequent 1-itemsets), then iteratively build $L_{k+1}$ from $L_k$ by joining and pruning candidates via monotonicity. Terminate when $L_k = \emptyset$.
> - **Weakness:** many DB passes; candidate explosion in dense data.
> - **FP-Growth:** builds a compact FP-tree in 2 passes; mines patterns via conditional trees. Faster in practice.
> - **Interestingness ≠ confidence.** High-confidence rules can be trivially explained by high support of $Y$. Use **lift** or **conviction** as tie-breakers.

> [!summary] Summary
> Frequent-itemset mining searches for co-occurring items above a *support* threshold. Apriori exploits monotonicity — no frequent superset can have an infrequent subset — to prune the candidate lattice. Confidence measures conditional likelihood of the consequent but is misleading without lift. FP-Growth avoids Apriori's multiple database passes via an FP-tree structure.

> [!todo] Follow-ups
> - [ ] Solve exercise 02 (Apriori by hand on toy DB)
> - [ ] Implement FP-Growth in Python, compare to mlxtend
> - [ ] Compare lift/conviction on the "Groceries" dataset
