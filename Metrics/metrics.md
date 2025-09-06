# Evaluation Metrics

Given:

* $G$: the set of gold-standard axioms,
* $P$: the set of predicted axioms,
* An axiom $m = (C, R, O)$, where $C$ is a class (subject), $R$ a property (predicate), and $O$ either a class (object property) or a datatype (attribute).

## Weighted Precision, Recall and F1-score

We define a similarity function $\text{sim}(p,g) \in \{0,0.5,1\}$ between a predicted axiom $p \in P$ and a gold axiom $g \in G$:

$$
\text{sim}(p,g) =
\begin{cases}
1.0 & \text{if } (C_p = C_g) \wedge (R_p = R_g) \wedge (O_p = O_g) \\
0.5 & \text{if } (C_p = C_g) \wedge (O_p = O_g) \wedge (R_p \neq R_g) \\
0.0 & \text{otherwise}
\end{cases}
$$

Weighted precision and recall are:

$$
\text{Precision}_w = \frac{1}{|P|} \sum_{p \in P} \max_{g \in G} \text{sim}(p,g)
$$

$$
\text{Recall}_w = \frac{1}{|G|} \sum_{g \in G} \max_{p \in P} \text{sim}(g,p)
$$

Weighted F1 is:

$$
F1_w = \frac{2 \cdot \text{Precision}_w \cdot \text{Recall}_w}{\text{Precision}_w + \text{Recall}_w}
$$

---

### Coverage with Penalty for Extra Predictions

$$
\text{Coverage}_{class} = \frac{|Classes_{covered}|}{|Classes_{Gold}| + |Classes_{Predicted}^{unique}|}
$$

$$
\text{Coverage}_{rel} = \frac{|Relations_{covered}|}{|Relations_{Gold}| + |Relations_{Predicted}^{unique}|}
$$

$$
\text{Coverage}_{dt} = \frac{|DatatypeProperties_{covered}|}{|DatatypeProperties_{Gold}| + |DatatypeProperties_{Predicted}^{unique}|}
$$

where:

* $Classes_{covered}$ = gold classes correctly matched by predictions
* $Relations_{covered}$ = gold object properties correctly matched (included _subClassOf_)
* $DatatypeProperties_{covered}$ = gold datatype properties correctly matched,
* $Predicted^{unique}$ = elements predicted but not in the gold standard.

These metrics extend the standard binary evaluation by (i) rewarding partial matches between subject–object pairs with different predicates, and (ii) penalizing systems that introduce non-existing classes or properties. They can be reported in addition to standard precision, recall and F1 to provide a more fine-grained evaluation.
