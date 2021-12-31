# Definition

**Flow Networks**

A directed graph $G=(V,E)$, with the following features：

* capacity $c:E \rightarrow \mathbb{R}^+$
* a single source node $s \in V$
* a single sink node $t \in V$

Denoted $(G,c,s,t)$

**Flow**

An $s-t$ flow is a function $f:E\rightarrow \mathbb{R}^{+}$, satisfying the following two properties：

* For each $e\in E$, $0 \leq f(e) \leq c(e)$

* For each node $v$ other that $s$ and $t$, we have
    $$
    \sum_{e \in \delta^{-}(v)}f(e)=\sum_{e \in \delta^{+}(v)}f(e)
    $$

**value** of a flow $f$, denoted $v(f)$, defined by
$$
v(f)=\sum_{e\in \delta+(s)}f(e)
$$
**The Maximum-Flow Problem**

Instance: Flow network $(G,c,s,t)$

Task: Find a flow of maximum value

# Ford-Fulkerson Algorithm

**Residual graph $G_f$**

Given a flow network $(G,c,s,t)$ and a flow $f$, we define the residual graph $G_f$ of $G$ with respect to $f$ as follows.

* $V(G_f)=V(G)$

* **forward edges**

    $e=(u,v)\in E(G)$ on which $f(e)<c(e)$, there are $c_e-f(e)$ "<u>leftover</u>" capacity to push flow forward. 

    Including $e=(u,v)$ in $G_f$, with a capacity of $c_e-f(e)$, $e$ is a forward edge.

* **backward edges**

    $e=(u,v)\in G$ on which $f(e) > 0$, there are $f(e)$ flow that we can "<u>undo</u>" by pushing flow backward.

    Including $e'=(v,u)$ in $G_f$ (reversed), with a capacity of $f(e)$, $e'$ is a backward edge.

Notes

* **residual capacity** is the capacity of an edge in $G_f$
* $e\in E(G)$, if $0 < f(e) < c_e$, both a forward edge and a backward edge being included in $G_f$



