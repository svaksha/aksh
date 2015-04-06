# JULIA.md

* Julia instance, https://tmpnb.org/user-tMmHkibTA4kf/tree
* https://github.com/JuliaLang/julia/blob/master/CONTRIBUTING.md

----

# Algorithms
* Strassen algorithm for matrix multiplication in julia: https://gist.github.com/GaZ3ll3/87df748f76b119199fed
   - Jupyter NB: http://nbviewer.ipython.org/github/GaZ3ll3/Step_In_Julia/blob/master/notebook/Linear%20Algebra.ipynb

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

# Tests - core JULIA
* https://github.com/JuliaLang/julia/blob/master/test/unicode.jl
* https://github.com/JuliaLang/julia/blob/e0176ec9c44530f4474f2f347613de121f9ed1fc/test/pkg.jl
## Unit and Functional Testing
* http://julia.readthedocs.org/en/latest/stdlib/test/

----

# Documentation
* https://github.com/JuliaLang/julia/blob/ff9cebe45e6c39933ab26ca134b59b3ef47ec821/doc/helpdb.jl
julia> foo = "abc"; bar = "bac"; zoo = "234";

julia> if foo == "abc" && bar == "bac" && zoo != "123"
           println("Please see http://docs.julialang.org/en/latest/manual/control-flow/")
       end
See http://docs.julialang.org/en/latest/manual/control-flow/
Check out http://julia.readthedocs.org/en/release-0.3/manual/control-flow/#short-circuit-evaluation

### Good Example to start writing documentation
Here is an example of documentation for a package I maintain:

https://tshort.github.io/Sims.jl/

Here are examples of docstrings:

https://github.com/tshort/Sims.jl/blob/master/src/sim.jl#L1-L96

Here is the config file for Mkdocs:

https://github.com/tshort/Sims.jl/blob/master/mkdocs.yml

Here is a Julia script that uses the Lexicon package to build the API documentation from the docstrings:

https://github.com/tshort/Sims.jl/blob/master/docs/build.jl

Here are other packages that use Mkdocs:

https://www.google.com/search?q=mkdocs.yml+jl+site:github.com&ie=utf-8&oe=utf-8

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

# Arrays
+ http://julia.readthedocs.org/en/latest/manual/arrays/

+ https://en.wikipedia.org/wiki/Regular_expression#Syntax 
+ http://julia.readthedocs.org/en/latest/manual/strings/ 
+ https://stackoverflow.com/questions/20478823/joining-regular-expressions-in-julia

# RE
+ https://en.wikipedia.org/wiki/Regular_expression
