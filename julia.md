
+ Julia instance, https://tmpnb.org/user-tMmHkibTA4kf/tree
+ https://github.com/JuliaLang/julia/blob/master/CONTRIBUTING.md

----

# Algorithms
+ Strassen algorithm for matrix multiplication in julia: https://gist.github.com/GaZ3ll3/87df748f76b119199fed
   + Jupyter NB: http://nbviewer.ipython.org/github/GaZ3ll3/Step_In_Julia/blob/master/notebook/Linear%20Algebra.ipynb

----

# Bugs
+ https://github.com/JuliaLang/julia/issues?q=is%3Aopen+is%3Aissue+label%3A%22up+for+grabs%22
+ 9493 : https://github.com/JuliaLang/julia/issues/9493
+ 5840 : https://github.com/JuliaLang/julia/issues/5840

### JuliaWeb
+ https://github.com/JuliaWeb/Roadmap/issues

### Linear Algebra 
+ https://github.com/JuliaLang/julia/issues?q=is%3Aopen+label%3A%22up+for+grabs%22+is%3Aissue+label%3A%22linear+algebra%22
+ [Proposal: Better linear algebra benchmarks #4668](https://github.com/JuliaLang/julia/issues/4668)

----

# QA - core JULIA
+ https://github.com/JuliaLang/julia/blob/master/test/unicode.jl
+ https://github.com/JuliaLang/julia/blob/e0176ec9c44530f4474f2f347613de121f9ed1fc/test/pkg.jl

## Unit and Functional Testing
+ http://julia.readthedocs.org/en/latest/stdlib/test/

----

# Documentation
+ https://github.com/JuliaLang/julia/blob/ff9cebe45e6c39933ab26ca134b59b3ef47ec821/doc/helpdb.jl
```
julia> foo = "abc"; bar = "bac"; zoo = "234";

julia> if foo == "abc" && bar == "bac" && zoo != "123"
           println("Please see http://docs.julialang.org/en/latest/manual/control-flow/")
       end
```
+ See http://docs.julialang.org/en/latest/manual/control-flow/
+ Check out http://julia.readthedocs.org/en/release-0.3/manual/control-flow/#short-circuit-evaluation

### Good Example to start writing documentation
+ Example of documentation for a package: https://tshort.github.io/Sims.jl/
+ Here are examples of docstrings: https://github.com/tshort/Sims.jl/blob/master/src/sim.jl#L1-L96
+ Here is the config file for Mkdocs: https://github.com/tshort/Sims.jl/blob/master/mkdocs.yml
+ Here is a Julia script that uses the Lexicon package to build the API documentation from the docstrings: https://github.com/tshort/Sims.jl/blob/master/docs/build.jl
+ Here are other packages that use Mkdocs: https://www.google.com/search?q=mkdocs.yml+jl+site:github.com&ie=utf-8&oe=utf-8

----

# Packaging
+ http://docs.julialang.org/en/latest/manual/packages/#package-development
+ http://julia.readthedocs.org/en/latest/stdlib/pkg/
+ http://docs.julialang.org/en/latest/manual/packages/
+ Old SO thread: http://stackoverflow.com/questions/14092316/simplest-ways-to-make-a-julia-package-available-to-others

### build.jl
+ https://github.com/JuliaOpt/Ipopt.jl/blob/99b85463ca408aefb4931d2ebaaa97cf5f821acc/deps/build.jl#L42-L45

----

# API wrappers
+ https://github.com/svs14/Orchestra.jl/blob/master/src/python/scikit_learn.jl

----

# JuliaStats-Roadmap.jl
+ https://github.com/JuliaStats/Roadmap.jl/issues/11

----

# Arrays
+ http://julia.readthedocs.org/en/latest/manual/arrays/
+ https://julia.readthedocs.org/en/latest/stdlib/arrays
+ http://quant-econ.net/jl/julia_arrays.html
+ http://en.wikibooks.org/wiki/Introducing_Julia/Arrays_and_tuples
+ Read .csv, http://randyzwitch.com/julia-import-data/
+ DF, https://github.com/JuliaStats/DataFrames.jl/blob/cac96119c9f5e24c5f2976ff119703a6ec52476c/src/abstractdataframe/abstractdataframe.jl#L67
+ https://stackoverflow.com/questions/24275980/slice-array-of-arrays-in-julia

----

# LIB 
+ Abstract types: http://julia.readthedocs.org/en/latest/manual/types/#abstract-types
+ Punctuation, http://julia.readthedocs.org/en/latest/stdlib/punctuation/
+ Metaprogramming, http://julia.readthedocs.org/en/latest/manual/metaprogramming/

### RE Strings
+ http://julia.readthedocs.org/en/latest/stdlib/strings/
+ http://julia.readthedocs.org/en/latest/manual/strings/ 
+ https://stackoverflow.com/questions/20478823/joining-regular-expressions-in-julia

----

# Samskrit

+ [Unicode equivalence](http://en.wikipedia.org/wiki/Unicode_equivalence)
+ http://en.wikipedia.org/wiki/Sanskrit#Phonology
+ http://en.wikipedia.org/wiki/Unicode_equivalence
+ https://en.wikipedia.org/wiki/Devanagari#Unicode
+ http://www.unicode.org/charts/PDF/U0900.pdf
+ https://en.wikipedia.org/wiki/Sanskrit_grammar#Compounds_.28sam.C4.81sa.29
+ http://unicode.org/faq/indic.html

## SA-Papers
+ [A Deterministic Dependency Parser with Dynamic Programming for Sanskrit](http://www.aclweb.org/anthology/W13-3718), Amba Kulkarni, Department of Sanskrit Studies, University of Hyderabad, <apksh@uohyd.ernet.in>. Proceedings of the Second International Conference on Dependency Linguistics (DepLing 2013), pages 157–166, Prague, August 27–30, 2013; Charles University in Prague, Matfyzpress, Prague, Czech Republic.
+ [Parsing Sanskrit texts: Some relation speciﬁcissues](http://www.academia.edu/2683988/Parsing_Sanskrit_texts_Some_relation_specific_issues)
+ [ANALYSIS OF SANSKRIT TEXT : PARSING AND SEMANTIC RELATIONS](http://sanskrit.inria.fr/Symposium/DOC/Behera.pdf)

## Pingala-Fibonacci
+ http://en.wikipedia.org/wiki/Pingala#Combinatorics
+ http://en.wikipedia.org/wiki/Virahanka
+ [Origins of Fibonacci number](http://en.wikipedia.org/wiki/Fibonacci_number#Origins)
+ http://en.wikipedia.org/wiki/Backus%E2%80%93Naur_Form
+ http://en.wikibooks.org/wiki/Algorithm_Implementation/Mathematics/Fibonacci_Number_Program#Python
+ http://en.wikipedia.org/wiki/List_of_ancient_Indian_writers

##### Books
+ [Toward a Global Science: Mining Civilizational Knowledge By Susantha Goonatilake](http://books.google.co.in/books?id=SI5ip95BbgEC&pg=PA126&dq=Virahanka+Fibonacci&hl=en#v=onepage&q&f=false

----

# Images
+ [Installing Image Magick on Ubuntu 14.04](https://gist.github.com/rodleviton/74e22e952bd6e7e5bee1)

----

