+ [Graph Families](#graph-families)
+ [NP-complete](#np-complete)
+ [NP-hard](#np-hard)

----

# [Graph Families](https://en.wikipedia.org/wiki/Category:Graph_families)
+ https://en.wikipedia.org/wiki/Category:Parametric_families_of_graphs
+ https://en.wikipedia.org/wiki/Kneser_graph
+ [Graph Theory](https://en.wikipedia.org/wiki/Graph_theory)

+ https://en.wikipedia.org/wiki/Bipartite_graph
+ HW Questions:
    + http://www.cs.ecu.edu/~hochberg/spring2009/PythonPrograms.pdf
    + http://www.ics.uci.edu/~dechter/publications/r207.pdf
+ http://arxiv.org/pdf/1409.0173.pdf
+ https://www.codechef.com/MAY10/problems/GST/
+ http://www-inst.cs.berkeley.edu/~cs170/fa14/misc/final-sol.pdf
+ http://math.stackexchange.com/questions/436070/maximum-vertex-cover
+ http://theory.stanford.edu/~trevisan/cs261/lecture14.pdf
+ http://math.stackexchange.com/questions/210160/what-is-the-node-weight-of-a-vertex
+ http://www.brpreiss.com/books/opus4/html/page546.html
+ http://codeforces.com/blog/entry/18425
+ http://www.boost.org/doc/libs/1_46_1/libs/graph/example/undirected.cpp
+ http://www.quora.com/How-can-I-implement-a-weighted-directed-graph-in-C++-or-Java-using-object-oriented-programming
+ https://quickgrid.wordpress.com/2015/05/30/inputting-directed-undirected-weighted-and-unweighted-graph-in-c-c-adjacency-matrix/
+ http://stanford.edu/~stepp/cppdoc/BasicGraph-class.html
+ http://www.sanfoundry.com/cpp-programming-examples-graph-problems-algorithms/

----

# NP-complete
+ Karp's 21 NP-complete problems : https://en.wikipedia.org/wiki/Karp's_21_NP-complete_problems

## Maximum [weighted independent subset](https://en.wikipedia.org/wiki/Independent_set_%28graph_theory%29) theory
+ http://iss.ices.utexas.edu/?p=projects/galois/benchmarks/independent_set
+ http://www3.cs.stonybrook.edu/~algorith/files/independent-set.shtml
+ https://en.wikipedia.org/wiki/Clique_%28graph_theory%29
+ http://en.wikipedia.org/wiki/Maximum_clique
+ Paper: "Algorithm for finding cliques", http://www.imsc.res.in/~pptale/documents/report_ISI.pdf
+ https://en.wikipedia.org/wiki/Maximal_independent_set
+ https://en.wikipedia.org/wiki/Matching_%28graph_theory%29
+ https://wincent.com/wiki/Computing_the_Maximum_Weighted_Independent_Set_of_a_graph_path
+ https://www.google.co.in/search?client=ubuntu&channel=fs&q=+Find+a+subset+of+V+that+maximizes+the+sum+of+vertex+weights+without+any+two+vertices+in+that+subset+being+adjacent.&ie=utf-8&oe=utf-8&gfe_rd=cr&ei=pprtVc6HN7Hv8wfJsYWoCQ#q=Find+a+subset+of+V+that+maximizes+the+sum+of+vertex+weights+without+any+two+vertices+in+that+subset+being+adjacent.&channel=fs&start=30
+ A [vertex cover](https://en.wikipedia.org/wiki/Vertex_cover) (sometimes node cover) of a graph is a set of vertices such that each edge of the graph is incident to at least one vertex of the set. 
+ [Weighted Vertex Normals](http://www.bytehazard.com/articles/vertnorm.html)
   + [Surface Normal Vectors](https://en.wikipedia.org/wiki/Normal_%28geometry%29) are used in computer graphics to determine a surface's orientation toward a light source for flat shading, or the orientation of each of the corners (vertices) to mimic a curved surface with [Phong shading](https://en.wikipedia.org/wiki/Phong_shading) - an interpolation technique for surface shading in 3D computer graphics. Phong interpolation or normal-vector interpolation shading, interpolates surface normals across rasterized polygons and computes pixel colors based on the interpolated normals and a reflection model.

----

# [NP-hard](https://en.wikipedia.org/wiki/NP-hard)
+ https://en.wikipedia.org/wiki/NP-hard#NP-naming_convention
+ [All-Pairs Bottleneck Paths in Vertex Weighted Graphs](http://www.math.tau.ac.il/~asafico/bottle.pdf), Asaf Shapira, Raphael Yuster, Uri Zwick.
+ 1990 : [SPARSEST CUTS AND BOTTLENECKS IN GRAPHS](http://ac.els-cdn.com/0166218X9090133W/1-s2.0-0166218X9090133W-main.pdf?_tid=196f5ea0-4d71-11e5-8a1d-00000aab0f6c&acdnat=1440758565_1996876e0681c341b61aef7a39b1babb), David W. MATULA, Farhad SHAHROKHI.
+ 1998May15 : [Maximum vertex-weighted matching in strongly chordal graphs](http://ac.els-cdn.com/S0166218X97001364/1-s2.0-S0166218X97001364-main.pdf?_tid=8f64dcc6-4d7f-11e5-b2b0-00000aacb360&acdnat=1440764776_524bfd9783357f296c58ac41d8cdd59d), Manoel B. Campêlo, Sulamita Klein; Discrete Applied Mathematics, Volume 84, Issues 1–3, Elsevier Science B.V., All rights reserved.
    + __Abstract__ : Given a graph G = (V, E) and a real weight for each vertex of G, the vertex-weight of a matching is defined to be the sum of the weights of the vertices covered by the matching. In this paper we present a linear time algorithm for finding a maximum vertex-weighted matching in a strongly chordal graph, given a strong elimination ordering. The algorithm can be specialized to find a maximum cardinality matching, yielding an algorithm similar to one proposed earlier by Dahlhaus and Karpinsky. The technique does not seem to apply to the case of general edge-weighted matchings.
+ 2005 : [The Generalized Subgraph Problem: Valid inequalities and separation](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.330.1703), by Corinne Feremans , Martine Labbé , Adam Letchford , Juan-josé Salazar-gonzález.
   + __Abstract__ : This paper is concerned with a problem on networks which we call the Generalized Subgraph Problem (GSP). The GSP is defined on an undirected graph where the vertex set is partitioned into clusters. The task is to find a subgraph which touches at most one vertex in each cluster so as to maximize the sum of vertex and edge weights. The GSP, which is strongly N P-hard, is a natural relaxation of several important problems of a ‘generalized’ type. In this paper, we examine the GSP from a polyhedral viewpoint. We examine two 0-1 integer programming formulations and derive classes of valid and facet-inducing inequalities. We also give complete linear descriptions for some special cases. Finally, we give some results concerning the separation of these inequalities.
+ 2010jul08 : [Online Vertex-Weighted Bipartite Matching and Single-bid Budgeted Allocations](http://www.gagangoel.com/papers/online_vertex_weighted_soda2011.pdf), Gagan Aggarwal, Gagan Goel, Chinmay Karande, Aranyak Mehta; arXiv:1007.1271v1.

----


