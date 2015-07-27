
+ Julia instance, https://tmpnb.org/user-tMmHkibTA4kf/tree
+ https://github.com/JuliaLang/julia/blob/master/CONTRIBUTING.md

----

# BUGS
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

# Writing Documentation
+ https://github.com/JuliaLang/julia/pull/11906
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
+ HowTo document a package: https://tshort.github.io/Sims.jl/
+ Examples of docstrings: https://github.com/tshort/Sims.jl/blob/master/src/sim.jl#L1-L96
+ A Julia script that uses the Lexicon package to build the API documentation from the docstrings: https://github.com/tshort/Sims.jl/blob/master/docs/build.jl
+ Packages that use Mkdocs: https://www.google.com/search?q=mkdocs.yml+jl+site:github.com&ie=utf-8&oe=utf-8
+ A config file for Mkdocs: https://github.com/tshort/Sims.jl/blob/master/mkdocs.yml

### BR
+ http://doodlingindata.com/2014/12/29/documenting-julia-code/
+ https://github.com/JuliaLang/julia/issues/8965#issuecomment-67745941

----

# Packaging
+ http://docs.julialang.org/en/latest/manual/packages/#package-development
+ http://julia.readthedocs.org/en/latest/stdlib/pkg/
+ http://docs.julialang.org/en/latest/manual/packages/
+ Old SO thread: http://stackoverflow.com/questions/14092316/simplest-ways-to-make-a-julia-package-available-to-others

To move a large number of packages installed on the old system to a new one, do `Pkg.init()`, then copy only the `REQUIRE` file from `~/.julia/v0.x/` folder, then do a `Pkg.update()` on the cli.

## REQUIRE
+ https://github.com/JuliaLang/METADATA.jl/issues/2777
+ add to REQUIRE a package which isn't in METADATA, https://github.com/JuliaLang/julia/issues/7737

### Bugs
+ Rewrite Pkg.add to include repo argument [BUG # 11914](https://github.com/JuliaLang/julia/issues/11914).

### build.jl
+ https://github.com/JuliaOpt/Ipopt.jl/blob/99b85463ca408aefb4931d2ebaaa97cf5f821acc/deps/build.jl#L42-L45

### Using VS. import VS. importall
+ https://github.com/JuliaLang/julia/issues/11031 
+ https://github.com/JuliaLang/julia/issues/8000

From Leah:
I think his summary in #11031 is accurate, and the reason given directly in the reply is the reason for using/importall to be different. Issue #8000 is a discussion of ways to change/simplify the syntax.

I'll take a stab at rephrasing the different in case that helps. There is only one difference, and on the surface (syntax-wise) it may seem very minor. The difference between "using" and "importall" is that with "using" you need to say "function Foo.bar(.." to extend module Foo's function bar with a new method, but with "importall" or "import Foo.bar", you only need to say "function bar(..." and it automatically extends module Foo's function bar.

If you use "importall", then "function Foo.bar(..." and "function bar(..." become equivalent. If you use "using", then they are different.

The reason this is important enough to have been given separate syntax is that you don't want to accidentally extend a function that you didn't know existed, because that could easily cause a bug. This is most likely to happen with a method that takes a common type like string or int, because both you and the other module could define a method to handle such a common type. If you use importall, then you'll replace the other module's implementation of "bar(s::String)" with your new implementation, which could easily do something complete different (and break all/many future usages of the other functions in module Foo that depend on calling bar).

----

# API wrappers
+ https://github.com/svs14/Orchestra.jl/blob/master/src/python/scikit_learn.jl

----

# JuliaStats-Roadmap.jl
+ https://github.com/JuliaStats/Roadmap.jl/issues/11

----

# Array
+ http://julia.readthedocs.org/en/latest/manual/arrays/
+ https://julia.readthedocs.org/en/latest/stdlib/arrays
+ http://quant-econ.net/jl/julia_arrays.html
+ http://en.wikibooks.org/wiki/Introducing_Julia/Arrays_and_tuples
+ Read .csv, http://randyzwitch.com/julia-import-data/
+ DF, https://github.com/JuliaStats/DataFrames.jl/blob/cac96119c9f5e24c5f2976ff119703a6ec52476c/src/abstractdataframe/abstractdataframe.jl#L67
+ https://stackoverflow.com/questions/24275980/slice-array-of-arrays-in-julia

## Bugs
+ #7941:Towards array nirvana, https://github.com/JuliaLang/julia/issues/7941
+ https://github.com/JuliaLang/julia/issues/9874#issuecomment-75979041
+ {7} https://github.com/JuliaLang/julia/issues/3701
+ {8} https://github.com/JuliaLang/julia/issues/4774
+ {9} https://github.com/JuliaLang/julia/pull/7568
+ {10} https://github.com/JuliaLang/julia/pull/10525
+ {11} https://groups.google.com/forum/#!topic/julia-dev/sM0VyVbFewQ

----

# Lib INDEX
+ Index : http://julia.readthedocs.org/en/latest/genindex/
+ http://julia.readthedocs.org/en/latest/stdlib/base/
+ http://stackoverflow.com/questions/25716547/type-i-discrete-cosine-transform-not-defined-found-in-julia-0-3-0

# Syntax

+ http://julia.readthedocs.org/en/latest/manual/noteworthy-differences/
+ http://docs.julialang.org/en/latest/manual/integers-and-floating-point-numbers/
+ Abstract types: http://julia.readthedocs.org/en/latest/manual/types/#abstract-types
+ Punctuation, http://julia.readthedocs.org/en/latest/stdlib/punctuation/
+ Metaprogramming, http://julia.readthedocs.org/en/latest/manual/metaprogramming/
+ Arguments of mathematical operators to a common type, https://julia.readthedocs.org/en/latest/manual/conversion-and-promotion/

### Conditionals
+ http://slendermeans.org/julia-iterators.html
+ http://julia.readthedocs.org/en/latest/manual/control-flow/#man-loops   
+ https://en.wikibooks.org/wiki/Introducing_Julia/Controlling_the_flow

### RE Strings
+ http://julia.readthedocs.org/en/latest/stdlib/strings/
+ http://julia.readthedocs.org/en/latest/manual/strings/ 
+ https://stackoverflow.com/questions/20478823/joining-regular-expressions-in-julia

### Discussion: Multiple dispatch vs Single Dispatch syntax.
For starters, what something should belong to is not always unambiguous - viz. should a function that splits string a at every occurrence of b be a.split(b) or b.split(a)? None of the solutions is inherently significantly better than the other. 

More importantly, search in Julia does not belong to either "Hello World" or e. It belongs to the current namespace. In OOP languages, x.f(y) is the combination of two things: f being under the namespace of x, and f being defined as f(self, y). self is then substituted with x, and so it effectively devolves to f(x, y). Classes are used as proxy namespaces, so that search would be held in the namespace of the string classed object "Hello World" in your example. The benefit of that is that you know where to look for the function. In Julia, there's an overarching namespace. There is an expense associated with that, which is why OOP languages do what they do. But just by changing how we express f(x, y) to x.f(y) or y.f(x) actually doesn't change any of that. Nothing short of actually implementing a full-blown class system with behaviours that properly 'belong to' classes does. Which is not what the design decision was when Julia was started. As such, while I like the syntactic simplification involved here, I just can't see how it would be either trivial but useless or useful but subverting some fundamental underlying design decisions

----

# GIST
+ cprintf.jl, https://gist.github.com/dpo/11000433

#### Algorithms
+ Strassen algorithm for matrix multiplication in julia: https://gist.github.com/GaZ3ll3/87df748f76b119199fed
   + Jupyter NB: http://nbviewer.ipython.org/github/GaZ3ll3/Step_In_Julia/blob/master/notebook/Linear%20Algebra.ipynb

----

# Math

## Integral
+ http://docs.julialang.org/en/latest/stdlib/math/#numerical-integration

----


