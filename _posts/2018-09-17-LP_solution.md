## Concept for solutions of linear programming 

In this article, I want to clear up the logical framework of LP solutions and try to elaborate on some intuitionistic understandings. For the intuition, I specifically allude to the two-dimension graphical representation.

To set-up the LP structure, there is a universal *standard form* for all the LP problems.
$$
\max_\mathbf{x}: \mathbf{c}^\intercal \cdot \mathbf{x} \\
s.t. \quad \mathbf{A} \cdot \mathbf{x} = \mathbf{b} \\
     \quad \mathbf{x} \geq \mathbf0
$$
$\mathbf{x}$ is the vector with all the *decision varibles* to select out; $\mathbf{c}^\intercal \cdot \mathbf{x}$ is the *objective function* to maximize where $\mathbf{c}$ is the respective coefficients for decision variables;  $\mathbf{A} \cdot \mathbf{x} = \mathbf{b}$ is the total *constraint*, which is the most subtle part for LP. 

$\mathbf{A} \cdot \mathbf{x} = \mathbf{b}$  and  $\mathbf{x} \geq \mathbf0$ together define a feasible region for $\mathbf{x}$, and in geometry sense, it is called *polyhedron* $\mathbf{P}$, polyhedron is the fundamental space for LP. For 2-dimention case, it could be representead as the yellow area:

![feasible_region](feasible_region.png)

There is a generalization for the LP solutions:
$$
Basic\:Solution \subset BFS = Extreme\:Point / Vertices\subset Optimum
$$
The middle equivalence is the half core of LP solution as it bridges the *algebraic* concept of basic feasible solution (BFS) into $geometric$ definition of extreme point and vertice.  And the crucial right hand side subset relationship assures the feasiblity to find solution within BFS. 

### Definition

* Basic Solution:

  A vector $\hat{\mathbf{x}}$ is basic solution if it the set $\bar{\mathbf{A}}$  of column j of $\mathbf{A}$ where $\hat{X_j} \neq 0$ is **linearly independent**, i.e., full rank.

  For M constraints with N decision ($M > N$) variables to maximize, any set of N constraints in the M constraints that is linear independent uniquely identifies a basis solution. In 2-dimention case, basis solution is the *intersection point between pair lines* (N = 2 case, thus $C_M^2$ combination).

* Basis Feasible Solution - BFS

  basis solution vector $\hat{\mathbf{x}}$  that also satisfies the condition $\mathbf{x} \geq \mathbf0$.

* Extreme Points

  For *convex set* $\mathbb{S}$, if point $\mathbf{x}$ can not be writen as combination of points $\mathbf{y}$ and $\mathbf{z}$ of  $\mathbb{S}$, i.e., 

  $\mathbf{x} = \lambda \mathbf{y} + (1-\lambda)\mathbf{z} \quad for  \:\lambda \in (0,1)$, $\mathbf{x}$ is a extreme point.

  Extreme point could be interpreted as the endpoint of the line segements that intersect with $\mathbb{S}$.

* Vertices

  For $\mathbf{U}$ be a *polyhedron*, extreme points of $\mathbf{U}$ are just vertices of $\mathbf{U}$. Vertices are 'corner points'.





  ![vertices](/Users/lxh/Desktop/vertices.png)

###Equivalence

> Theorem
>
> $\mathbf{x} \in P \equiv \{ \mathbf{x} : \mathbf{A} \cdot \mathbf{x} = \mathbf{b},\: \mathbf{x} \geq \mathbf0\} $ is an **extreme point** if and only if $\mathbf{x}$ is a **basic feasible solution**, i.e., the set $\bar{\mathbf{A}}$  of column j of $\mathbf{A}$ where $\hat{X_j} \neq 0$ is linearly independent 

Proof by contradiction.



### Optimum Existence in Vertex

* *Unbounded case with no optimum

In the first place, distinguish between bounded and unbounded polyhedron, for unbounded set, there may be infinite value ($+\infty$).

> Representation:
> $$
> \forall \: \mathbf{x} \in P, \quad
> \mathbf{x} = \sum \lambda_i v_i + \mathbf{d}  \\ 
> where \: \sum \lambda_i = 1, \lambda_i \:\geq0 \: for \: all \:i \\
> \quad \{ V_i \} \: is \: the \: vertex \: set \\
> \mathbf{d} =  \: direction \: or \: \mathbf{0}
> $$
>

If $\mathbf{c}^\intercal \cdot \mathbf{d} >  0$, maximal value $\rightarrow + \infty$, no optimal solution. 



* Optimum is the subset of vertices

> lemma:  if $P \equiv \{ \mathbf{x} : \mathbf{A} \cdot \mathbf{x} = \mathbf{b},\: \mathbf{x} \geq \mathbf0\} \neq \emptyset$ , $\mathbf{P}$ has at least one vertex.  *affirm the existence of vertex at polyhedron*
>
>
>
> Theorem:
>
> optimum of LP (maximal value for $\mathbf{c}^\intercal \cdot \mathbf{x}$) is attained at *vertex* of polyhedron P.    

 

Proof by:

 	1.  represent $\mathbf{x}$ with linear combination of vertices: $
      \mathbf{x} = \sum \lambda_i v_i$ 
 	2.  compare with the maximal vertex $V^*\equiv argmax\{ \mathbf{c}^\intercal \cdot V_i  \}$ 