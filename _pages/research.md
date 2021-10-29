---
permalink: /research
title: "Research"
excerpt: "Research"
author_profile: true
---

Crystals
------

While the definition of the *crystal basis* is purely algebraic and starts with
a suitable $U_q(\mathfrak{g})$-module, an *abstract crystal* is mainly what I work
with and can be defined in the following combinatorial way.  Suppose $\mathfrak{g}$ is a
symmetrizable Kac-Moody algebra with weight lattice $P$ and simple positive
roots indexed by the set $I$.  An abstract crystal $B$ associated to $\mathfrak{g}$ is a
nonempty set equipped with

- maps $e_i,f_i\colon B \longrightarrow B\sqcup\\{\boldsymbol{0}\\}$ ($i\in I$), called
*Kashiwara operators*, which mimic the multiplication on the left of
Chevalley generators $E_i$ and $F_i$ from $U_q(\mathfrak{g})$;
- maps $\varepsilon_i,\varphi_i\colon B \longrightarrow \mathbf{Z} \sqcup\\{-\infty\\}$;
- and a weight map $\mathrm{wt}\colon B \longrightarrow P$.

These maps satisfy a number of axioms, including, for all $x,y\in B$ and
$i\in I$, we have $f_ix = y$ if and only if $e_iy = x$,
$\mathrm{wt}(f_ix) = \mathrm{wt}(x) - \alpha_i$.  The former condition allows $B$ to be
equipped with an $I$-colored graph structure such that there is an $i$-colored
arrow in the graph from $x$ to $y$ if and only if $f_ix = y$.

```python
sage: B = crystals.infinity.Tableaux(['A',2])
sage: b = B.highest_weight_vector()
sage: T = crystals.elementary.T(['A',2], B.Lambda()[1] + B.Lambda()[2])
sage: t = T[0]
sage: C = crystals.elementary.Component(['A',2])
sage: c = C[0]
sage: TP = crystals.TensorProduct(C,T,B)
sage: t0 = TP(c,t,b)
sage: STP = TP.subcrystal(generators=[t0])
sage: GTP = TP.digraph(subset=STP)
sage: view(GTP, tightpage=True) # optional - dot2tex graphviz, not tested (opens external window)
```
