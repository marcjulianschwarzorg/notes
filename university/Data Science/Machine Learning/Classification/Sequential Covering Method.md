---
uni-module: "KDD"
---

# Sequential Covering Method

Extracts [[IF-THEN Rules for Classification]] directly from training data. It works by sequentially generating rules and removing positive target tuples that satisfy the generated rule.

Now rules are being generated by, at each iteration, finding the best predicate $p$ according to the _FOIL_Gain_ measure and adding it to the current rule if it exceeds a given threshold.

$$\text{FOIL Gain}=\operatorname{pos}^{\prime}\left(\log _2 \frac{\operatorname{pos}^{\prime}}{\operatorname{pos}^{\prime}+\text { neg }^{\prime}}-\log _2 \frac{\text { pos }}{\text { pos }+\text { neg }}\right) .$$
This measure favors rules with high [[Accuracy]] and rules which cover many positive tuples.

Of course this method can also lead to [[Overfitting]]. Thus, rules for which _FOIL_Prune_ is higher for the pruned version, have to be pruned (removing a conjunct from the rule).

$$\text { FOIL Prune }(R)=\frac{\text { pos }-\text { neg }}{\text { pos }+\text { neg }}$$

> [!TIP]- Algorithm Examples
>
> - FOIL
> - AQ
> - CN2
> - RIPPER

## Visual

![[Bildschirmfoto 2022-10-16 um 21.19.13.png]]
