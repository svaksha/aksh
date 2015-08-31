+ [Arithmetic](#Arithmetic)
+ [Calculus and Analysis](#calculus-and-analysis)
+ [Calculus-II](#calculus-ii)
+ [Combinatorics](#combinatorics)
   + [Graph Theory](#graph-theory)
        + [NP-complete](#np-complete)
        + [NP-hard](#np-hard)
+ [Geometry](#geometry)
+ [Linear Algebra](#linear-algebra)
+ [PAPERS](#papers)
+ [Type Theory](#type-theory)

---- 

# Arithmetic
+ [A "two-product" style algorithm paper](http://www.ti3.tu-harburg.de/paper/rump/OgRuOi05.pdf).

----

# Calculus and Analysis
+ https://en.wikipedia.org/wiki/Lambda_calculus
+ http://tutorial.math.lamar.edu/Classes/Calci/RateOfChange.aspx
+ https://en.wikipedia.org/wiki/Antiderivative
+ [ceil](https://en.wikipedia.org/wiki/Floor_and_ceiling_functions) and the [matlab definition](https://www.mathworks.com/help/matlab/ref/ceil.html)

# Calculus-II
+ Calculus-II course at Lamar University: http://tutorial.math.lamar.edu/Classes/CalcII/CalcII.aspx

### Integral Transforms
+ https://en.wikipedia.org/wiki/Exponential_integral
+ https://en.wikipedia.org/wiki/Integral_geometry
+ http://mathworld.wolfram.com/IntegralTransform.html
+ http://www.encyclopediaofmath.org/index.php/Singular_integral_equation

---- 

# [Combinatorics](https://en.wikipedia.org/wiki/Category:Combinatorics) 

## [Graph Theory](https://en.wikipedia.org/wiki/Graph_theory)
+ https://en.wikipedia.org/wiki/Bipartite_graph
+ https://en.wikipedia.org/wiki/Clique_%28graph_theory%29
+ Paper: "Algorithm for finding cliques", http://www.imsc.res.in/~pptale/documents/report_ISI.pdf

### NP-complete
+ Karp's 21 NP-complete problems : https://en.wikipedia.org/wiki/Karp's_21_NP-complete_problems
+ The maximum [weighted independent subset](https://en.wikipedia.org/wiki/Independent_set_%28graph_theory%29) theory : In graph theory, an independent set or stable set is a set of vertices in a graph, no two of which are adjacent. That is, it is a set I of vertices such that for every two vertices in I, there is no edge connecting the two. Equivalently, each edge in the graph has at most one endpoint in I. The size of an independent set is the number of vertices it contains. Independent sets have also been called internally stable sets.
   + A maximal independent set is either an independent set such that adding any other vertex to the set forces the set to contain an edge or the set of all vertices of the empty graph. It is an independent set of largest possible size for a given graph G. This size is called the independence number of G, and denoted α(G).[2] The problem of finding such a set is called the maximum independent set problem and is an NP-hard optimization problem. As such, it is unlikely that there exists an efficient algorithm for finding a maximum independent set of a graph. Every maximum independent set also is maximal, but the converse implication does not necessarily hold.
   + http://iss.ices.utexas.edu/?p=projects/galois/benchmarks/independent_set
+ In the mathematical discipline of graph theory, a [vertex cover](https://en.wikipedia.org/wiki/Vertex_cover) (sometimes node cover) of a graph is a set of vertices such that each edge of the graph is incident to at least one vertex of the set. The problem of finding a minimum vertex cover is a classical optimization problem in computer science and is a typical example of an NP-hard optimization problem that has an approximation algorithm, whereas, its decision version, the vertex cover problem, was one of Karp's 21 NP-complete problems and is therefore a classical _NP-complete problem_ in computational complexity theory. Furthermore, the vertex cover problem is fixed-parameter tractable and a central problem in parameterized complexity theory.
+ [Weighted Vertex Normals](http://www.bytehazard.com/articles/vertnorm.html)
   + [Surface Normal Vectors](https://en.wikipedia.org/wiki/Normal_%28geometry%29) are used in computer graphics to determine a surface's orientation toward a light source for flat shading, or the orientation of each of the corners (vertices) to mimic a curved surface with [Phong shading](https://en.wikipedia.org/wiki/Phong_shading) - an interpolation technique for surface shading in 3D computer graphics. Phong interpolation or normal-vector interpolation shading, interpolates surface normals across rasterized polygons and computes pixel colors based on the interpolated normals and a reflection model.


### [NP-hard](https://en.wikipedia.org/wiki/NP-hard)
+ https://en.wikipedia.org/wiki/NP-hard#NP-naming_convention
+ [All-Pairs Bottleneck Paths in Vertex Weighted Graphs](http://www.math.tau.ac.il/~asafico/bottle.pdf), Asaf Shapira, Raphael Yuster, Uri Zwick.
+ 1990 : [SPARSEST CUTS AND BOTTLENECKS IN GRAPHS](http://ac.els-cdn.com/0166218X9090133W/1-s2.0-0166218X9090133W-main.pdf?_tid=196f5ea0-4d71-11e5-8a1d-00000aab0f6c&acdnat=1440758565_1996876e0681c341b61aef7a39b1babb), David W. MATULA, Farhad SHAHROKHI.
+ 1998May15 : [Maximum vertex-weighted matching in strongly chordal graphs](http://ac.els-cdn.com/S0166218X97001364/1-s2.0-S0166218X97001364-main.pdf?_tid=8f64dcc6-4d7f-11e5-b2b0-00000aacb360&acdnat=1440764776_524bfd9783357f296c58ac41d8cdd59d), Manoel B. Campêlo, Sulamita Klein; Discrete Applied Mathematics, Volume 84, Issues 1–3, Elsevier Science B.V., All rights reserved. 
    + __Abstract__ : Given a graph G = (V, E) and a real weight for each vertex of G, the vertex-weight of a matching is defined to be the sum of the weights of the vertices covered by the matching. In this paper we present a linear time algorithm for finding a maximum vertex-weighted matching in a strongly chordal graph, given a strong elimination ordering. The algorithm can be specialized to find a maximum cardinality matching, yielding an algorithm similar to one proposed earlier by Dahlhaus and Karpinsky. The technique does not seem to apply to the case of general edge-weighted matchings.
+ 2005 : [The Generalized Subgraph Problem: Valid inequalities and separation](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.330.1703), by Corinne Feremans , Martine Labbé , Adam Letchford , Juan-josé Salazar-gonzález. 
   + __Abstract__ : This paper is concerned with a problem on networks which we call the Generalized Subgraph Problem (GSP). The GSP is defined on an undirected graph where the vertex set is partitioned into clusters. The task is to find a subgraph which touches at most one vertex in each cluster so as to maximize the sum of vertex and edge weights. The GSP, which is strongly N P-hard, is a natural relaxation of several important problems of a ‘generalized’ type. In this paper, we examine the GSP from a polyhedral viewpoint. We examine two 0-1 integer programming formulations and derive classes of valid and facet-inducing inequalities. We also give complete linear descriptions for some special cases. Finally, we give some results concerning the separation of these inequalities.
+ 2010jul08 : [Online Vertex-Weighted Bipartite Matching and Single-bid Budgeted Allocations](http://www.gagangoel.com/papers/online_vertex_weighted_soda2011.pdf), Gagan Aggarwal, Gagan Goel, Chinmay Karande, Aranyak Mehta; arXiv:1007.1271v1.

----

# Geometry
+ [Chirality in MATH](http://en.wikipedia.org/wiki/Chirality_%28mathematics%29) and [Chirality in Organic Chemistry](http://en.wikipedia.org/wiki/Chirality_%28chemistry%29).
+ http://mathworld.wolfram.com/Slope.html
+ https://en.wikipedia.org/wiki/Integral_geometry
+ https://en.wikipedia.org/wiki/Geometric_Shapes

#### Papers
+ http://arxiv.org/pdf/1404.1499v2.pdf

----

# Linear Algebra
+ https://www.khanacademy.org/math/linear-algebra
   + Video : https://www.khanacademy.org/math/linear-algebra/matrix_transformations/linear_transformations/v/vector-transformations
+ https://en.wikipedia.org/wiki/Linear_algebra
+ https://en.wikipedia.org/wiki/Cholesky_decomposition
+ https://en.wikipedia.org/wiki/LU_decomposition
+ https://en.wikipedia.org/wiki/Matrix_%28mathematics%29
+ [Matrix and Linear Algebra](http://www.economics.soton.ac.uk/staff/aldrich/matrices.htm)

----

### sparse distributed matrix
+ https://en.wikipedia.org/wiki/Array_data_type
+ https://ch.mathworks.com/help/distcomp/sparse.html
+ https://ch.mathworks.com/help/distcomp/distributed.spalloc.html

----

# PAPERS
+ [Associative-Commutative Discrimination Nets](http://www.cs.tufts.edu/~nr/cs257/archive/leo-bachmair/ac-discrimination-nets.pdf)
+ Richard Jenk's paper ["A Pattern Compiler"](https://dl.acm.org/citation.cfm?id=806324&dl=ACM&coll=DL&CFID=621425526&CFTOKEN=54560421)


----

# [Type Theory](https://en.wikipedia.org/wiki/Category:Type_theory)
## [Data Types](https://en.wikipedia.org/wiki/Data_type)
+ https://en.wikipedia.org/wiki/Enumerated_type


