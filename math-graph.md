+ [Graph Theory](#graph-theory)
+ [NP-complete](#np-complete)
   + [Independent Set Graph](#independent-set-graph)
+ [NP-hard](#np-hard)
   + [Papers](#papers)
   
----

# [Graph Theory](https://en.wikipedia.org/wiki/Graph_theory)
+ [Graph Families](https://en.wikipedia.org/wiki/Category:Graph_families)
+ https://en.wikipedia.org/wiki/Category:Parametric_families_of_graphs
+ https://en.wikipedia.org/wiki/Kneser_graph
+ https://en.wikipedia.org/wiki/Bipartite_graph
+ HW Questions:
    + http://www.cs.ecu.edu/~hochberg/spring2009/PythonPrograms.pdf
    + http://www.ics.uci.edu/~dechter/publications/r207.pdf

----

# NP-complete
+ Karp's 21 NP-complete problems : https://en.wikipedia.org/wiki/Karp's_21_NP-complete_problems

## [Independent Set Graph](https://en.wikipedia.org/wiki/Independent_set_%28graph_theory%29)
+ http://iss.ices.utexas.edu/?p=projects/galois/benchmarks/independent_set
+ http://www3.cs.stonybrook.edu/~algorith/files/independent-set.shtml
+ https://en.wikipedia.org/wiki/Clique_%28graph_theory%29
+ http://en.wikipedia.org/wiki/Maximum_clique
+ Paper: "Algorithm for finding cliques", http://www.imsc.res.in/~pptale/documents/report_ISI.pdf
+ https://en.wikipedia.org/wiki/Maximal_independent_set
+ https://en.wikipedia.org/wiki/Matching_%28graph_theory%29
+ https://wincent.com/wiki/Computing_the_Maximum_Weighted_Independent_Set_of_a_graph_path
+ https://www.google.co.in/search?client=ubuntu&channel=fs&q=+Find+a+subset+of+V+that+maximizes+the+sum+of+vertex+weights+without+any+two+vertices+in+that+subset+being+adjacent.&ie=utf-8&oe=utf-8&gfe_rd=cr&ei=pprtVc6HN7Hv8wfJsYWoCQ#q=Find+a+subset+of+V+that+maximizes+the+sum+of+vertex+weights+without+any+two+vertices+in+that+subset+being+adjacent.&channel=fs&start=30
+ https://www.google.co.in/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=0CB8QFjAAahUKEwihyZzA0uzHAhWKJI4KHdoXAt0&url=http%3A%2F%2Fcodereview.stackexchange.com%2Fquestions%2F78292%2Fmax-independent-set-of-a-sequence&usg=AFQjCNEP_dDRJtDKyhAt4o2dcWPiHzejtA&bvm=bv.102022582,d.c2E

+ A [vertex cover](https://en.wikipedia.org/wiki/Vertex_cover) (sometimes node cover) of a graph is a set of vertices such that each edge of the graph is incident to at least one vertex of the set. 
+ [Weighted Vertex Normals](http://www.bytehazard.com/articles/vertnorm.html)
   + [Surface Normal Vectors](https://en.wikipedia.org/wiki/Normal_%28geometry%29) are used in computer graphics to determine a surface's orientation toward a light source for flat shading, or the orientation of each of the corners (vertices) to mimic a curved surface with [Phong shading](https://en.wikipedia.org/wiki/Phong_shading) - an interpolation technique for surface shading in 3D computer graphics. Phong interpolation or normal-vector interpolation shading, interpolates surface normals across rasterized polygons and computes pixel colors based on the interpolated normals and a reflection model.

### C-CPP
+ http://www.cplusplus.com/doc/tutorial/operators/  
+ http://www.boost.org/doc/libs/1_46_1/libs/graph/example/undirected.cpp
+ http://www.quora.com/How-can-I-implement-a-weighted-directed-graph-in-C++-or-Java-using-object-oriented-programming
+ https://quickgrid.wordpress.com/2015/05/30/inputting-directed-undirected-weighted-and-unweighted-graph-in-c-c-adjacency-matrix/
+ c++ code for MVC, http://www.gdeepak.com/thesisme/thesis-Choosing%20the%20Efficient%20Algorithm%20for%20Vertex%20Cover%20problem.pdf  
+ http://coderclubs.com/questions/1443550/maximum-bipartite-matching-c  to read

### Java
+ http://stackoverflow.com/questions/30412391/maximum-independent-set-weight

### links
+ http://theory.stanford.edu/~trevisan/cs261/lecture14.pdf
+ http://docs.scipy.org/doc/scipy/reference/stats.html
+ http://codereview.stackexchange.com/questions/78292/max-independent-set-of-a-sequence   imp OK....
+ http://shodhganga.inflibnet.ac.in/bitstream/10603/17548/21/21_%20appendix_02.pdf    imp 0k...
+ http://stackoverflow.com/questions/8593105/maximum-independent-set-algorithm
+ http://iswwwup.com/t/207afe252674/max-independent-set-of-a-sequence.html   imp ok
+ http://stackoverflow.com/questions/30921996/heuristic-to-find-the-maximum-weight-independent-set-in-an-arbritary-graph
+ http://www.wseas.org/multimedia/journals/mathematics/2012/55-232.pdf
+ http://ise.tamu.edu/people/faculty/butenko/yalta/slides/Trukhanov.pdf
+ http://www.quora.com/What-is-the-fastest-algorithm-to-enumerate-all-maximal-independent-sets-of-a-graph
+ http://wenda.baba.io/questions/2786226/finding-a-maximum-weight-clique-in-a-weighted-graph-c-sharp-implementation.html ..>pseudo code
+ https://hal.archives-ouvertes.fr/file/index/docid/905079/filename/preprint-AndreicaM-TowardsRealTimeSchedulingTreeNetworks.pdf   imp chordial
+ http://www.geeksforgeeks.org/largest-independent-set-problem/
+ https://github.com/jcoupey/mwis
+ https://www.cs.berkeley.edu/~vazirani/algorithms/chap6.pdf
+ http://arxiv.org/pdf/1409.0173.pdf
+ https://www.codechef.com/MAY10/problems/GST/
+ http://www-inst.cs.berkeley.edu/~cs170/fa14/misc/final-sol.pdf
+ http://math.stackexchange.com/questions/436070/maximum-vertex-cover
+ http://theory.stanford.edu/~trevisan/cs261/lecture14.pdf
+ http://math.stackexchange.com/questions/210160/what-is-the-node-weight-of-a-vertex
+ http://www.brpreiss.com/books/opus4/html/page546.html
+ http://codeforces.com/blog/entry/18425
+ http://stanford.edu/~stepp/cppdoc/BasicGraph-class.html
+ http://www.sanfoundry.com/cpp-programming-examples-graph-problems-algorithms/

### ToReadSearch
+ http://www.cise.ufl.edu/~sahni/dsaac/public/chapters/c20.pdf   
+ http://www.ibm.com/developerworks/library/os-giraph/   
+ https://github.com/networkx/networkx/tree/330fd210d29f5ca4d8f3bf9019cb4912b9f62fbe/doc/source  
+ http://stackoverflow.com/questions/6798953/program-of-recursion-for-maximum-independent-set-in-a-graph    code ex

----

# [NP-hard](https://en.wikipedia.org/wiki/NP-hard)
+ https://en.wikipedia.org/wiki/NP-hard#NP-naming_convention

### Papers
+ [All-Pairs Bottleneck Paths in Vertex Weighted Graphs](http://www.math.tau.ac.il/~asafico/bottle.pdf), Asaf Shapira, Raphael Yuster, Uri Zwick.
+ 1990 : [SPARSEST CUTS AND BOTTLENECKS IN GRAPHS](http://ac.els-cdn.com/0166218X9090133W/1-s2.0-0166218X9090133W-main.pdf?_tid=196f5ea0-4d71-11e5-8a1d-00000aab0f6c&acdnat=1440758565_1996876e0681c341b61aef7a39b1babb), David W. MATULA, Farhad SHAHROKHI.
+ 1998May15 : [Maximum vertex-weighted matching in strongly chordal graphs](http://ac.els-cdn.com/S0166218X97001364/1-s2.0-S0166218X97001364-main.pdf?_tid=8f64dcc6-4d7f-11e5-b2b0-00000aacb360&acdnat=1440764776_524bfd9783357f296c58ac41d8cdd59d), Manoel B. Campêlo, Sulamita Klein; Discrete Applied Mathematics, Volume 84, Issues 1–3, Elsevier Science B.V., All rights reserved.
    + __Abstract__ : Given a graph G = (V, E) and a real weight for each vertex of G, the vertex-weight of a matching is defined to be the sum of the weights of the vertices covered by the matching. In this paper we present a linear time algorithm for finding a maximum vertex-weighted matching in a strongly chordal graph, given a strong elimination ordering. The algorithm can be specialized to find a maximum cardinality matching, yielding an algorithm similar to one proposed earlier by Dahlhaus and Karpinsky. The technique does not seem to apply to the case of general edge-weighted matchings.
+ 2005 : [The Generalized Subgraph Problem: Valid inequalities and separation](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.330.1703), by Corinne Feremans , Martine Labbé , Adam Letchford , Juan-josé Salazar-gonzález.
   + __Abstract__ : This paper is concerned with a problem on networks which we call the Generalized Subgraph Problem (GSP). The GSP is defined on an undirected graph where the vertex set is partitioned into clusters. The task is to find a subgraph which touches at most one vertex in each cluster so as to maximize the sum of vertex and edge weights. The GSP, which is strongly N P-hard, is a natural relaxation of several important problems of a ‘generalized’ type. In this paper, we examine the GSP from a polyhedral viewpoint. We examine two 0-1 integer programming formulations and derive classes of valid and facet-inducing inequalities. We also give complete linear descriptions for some special cases. Finally, we give some results concerning the separation of these inequalities.
+ 2010jul08 : [Online Vertex-Weighted Bipartite Matching and Single-bid Budgeted Allocations](http://www.gagangoel.com/papers/online_vertex_weighted_soda2011.pdf), Gagan Aggarwal, Gagan Goel, Chinmay Karande, Aranyak Mehta; arXiv:1007.1271v1.

----

