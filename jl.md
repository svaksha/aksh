
+ Julia instance, https://tmpnb.org/user-tMmHkibTA4kf/tree
+ https://github.com/JuliaLang/julia/blob/master/CONTRIBUTING.md
   + https://github.com/IainNZ/ContributeToJulia
   
----

# 0.4-dev

Troubleshoot errors when running the unstable DEV branch

* https://github.com/QuantEcon/QuantEcon.jl/issues/64#issuecomment-130149602
* https://github.com/JuliaLang/julia/issues/12586

### ToDo Status

1. Closures : Functions with data inside (captured variables)
ex. adder(x) = y -> y+x
A function that returns an adding function. If you give x and it returns x after adding some data to it as the data is wrapped in it. Not sure how they relate to generic functions and methods

### HDF5
+ Array based storage using HDF5 and JLD
   * To use HDF5 (with JLD, which has been split recently), use Pkg.add("JLD") and in future, to use it say "using JLD" rather than "using HDF5, JLD."

### Current changes in 0.4

Your "subtype declaration" section is wrong: the abstract type does not define a block (you should just have "abstract Foo", not "abstract Foo ... end")

The "String" type is deprecated in favor of AbstractString in 0.4

[1:10] is deprecated in 0.4, in favor of [1:10;] to explicitly vcat.

You can just use +, not .+, for element-wise addition.  (It doesn't hurt to do .+, but it is unnecessary.)

help("func") is gone in 0.4

Pkg.build("Package") is useful to rebuild a package if the package build failed or your system configuration changed.

char(n) is deprecated in favor of Char(n) in 0.4

"Beware of multi-byte Unicode characters" is a bit misleading; it is not the Unicode "character" (technically you are referring to "codepoints") that is multi-byte, but rather the codepoint's encoding in UTF-8 (the default in Julia).  Maybe "Beware of multi-byte Unicode encodings in UTF-8"

(Of course, there are many other subtleties with Unicode: e.g. your example string "Ångström" can also be written "Ångström", which looks identical but actually uses a different set of codepoints via "combining characters".)

UintN in Julia 0.4 is deprecated in favor of UIntN (note caps).

Note there is also Complex{T}; Complex128 is just a shorthand for Complex{Float64}.

im is the "imaginary unit", not the "imaginary number".

eps() is an abbreviation for eps(Float64).  eps(T) is also defined for other types.

+ In 0.4, TypeName(val) automatically calls convert(TypeName, val) if no other constructor is available.   This also means that, when you are defining your own type, you should extend Base.convert if you have new conversions, rather than adding constructors.

+ eye(N) is an NxN identity; calling it "N-dimensional" may confuse people into thinking it returns an N-dimensional array.

+ M' is a synonym for ctranspose(M) (conjugate transpose).  M.' is transpose(M) without conjugation.  Of course, for real matrices they are equivalent.

+ Note that we can also do "for i in 1:10" ... this syntax is perhaps a bit clearer in that it generalizes to iterating over other kinds of containers.

+ To exit a loop you do "break", not "exit" (which is a function).

+ Functions with ! appended mutate at least one of their arguments.   Not necessarily the first one (e.g. see A_ldiv_B!), although this is the most common.

+ If you need tail-call optimization, it is more idiomatic to simply write a loop.

+ Instead of in(val,arr), you can simply do "val in arr"

+ The dictionary syntax has changed in 0.4: use Dict(a=>b, ...)

{...} is deprecated in 0.4.  Use Any[...].

it is more idiomatic to put "do" on the same line:

    map(collection) do elem
       ...
    end

You can override Base.show(io, ex) rather than Base.showerror.

+ "import ModuleName" does *not* import "all names".  It imports the module, but the only symbol imported is ModuleName itself; everything else must be accessed via ModuleName.something.

+ You should think of macros as being evaluated at parse-time, not run-time.  Basically:
    * a macro is a function evaluated at parse-time that takes an expression in and returns an expression out, and the latter is inserted into the parsed code.
    * a generated function is a function evaluated at compile-time which takes types in and returns an expression out, which is inserted into the code and compiled
    * an ordinary function is a function evaluated at run-time which takes values in and returns values out.

+ @test_approx_eq does not check equality to machine precision.  It checks equality at much lower precision.  In 0.4, you can also just use @test x ≈ y, where ≈ is \approx<tab> and is a synonym for the isapprox function.

+ The typical convention in Julia is to avoid underscores unless they are needed for readability.  i.e. we have iseven, not is_even.  This does not differ for variables vs. functions.

+ For performance, you should avoid abstract types in collections, but also as fields of types.

----

# BUGS
+ https://github.com/JuliaLang/julia/issues?q=is%3Aopen+is%3Aissue+label%3A%22up+for+grabs%22
+ 9493 : https://github.com/JuliaLang/julia/issues/9493
+ 5840 : https://github.com/JuliaLang/julia/issues/5840

### JuliaWeb
+ https://github.com/JuliaWeb/Roadmap/issues

### Linear Algebra 
+ https://github.com/JuliaLang/julia/issues?q=is%3Aopen+label%3A%22up+for+grabs%22+is%3Aissue+label%3A%22linear+algebra%22
+ #4668 [Proposal: Better linear algebra benchmarks](https://github.com/JuliaLang/julia/issues/4668)

----

# Writing Documentation
+ Moving Docstrings, https://github.com/JuliaLang/julia/pull/12703
+ https://github.com/JuliaLang/julia/pull/11943
+ https://github.com/JuliaLang/julia/pull/11906
+ https://github.com/JuliaLang/julia/blob/ff9cebe45e6c39933ab26ca134b59b3ef47ec821/doc/helpdb.jl

### @TeroFrondelius: When you want to contribute an example(s) to Julia's documentation, the process is following:
+ https://github.com/JuliaLang/julia/pull/12279#issuecomment-126058754
+ https://github.com/JuliaFEM/JuliaFEM.jl/pull/54

1) Create an account or sign in to GitHub https://github.com/ (my user name is TeroFrondelius and it's used from here on as an example)
2) Install Git to your computer https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
3) Fork Julia to your repository https://github.com/JuliaLang/julia 
4) Clone and build Julia from source to your computer (from your forked repository) https://github.com/JuliaLang/julia#source-download-and-compilation
     `git clone git@github.com:TeroFrondelius/julia.git`
     `cd julia`
     `make -j 8`
5) Find the function documentation, which you want to write an example. Let's say you want to write more examples for round() function http://julia.readthedocs.org/en/latest/stdlib/math/#Base.round: 
     `find -name *.rst | xargs grep "round("` (this will help you to locate the ./doc/stdlib/math.rst file where the round() function documentation is written. 
6) edit the ./doc/stdlib/math.rst with your favorite editor (i.e. Juno http://junolab.org/)
        .. doctest::

            julia> round(1.7)
            2.0
7) run the doctest using the command `make -C doc doctest` (and make sure your new doctest will pass)
8) Add updated files using command `git add ./doc/stdlib/math.rst` 
9) Commit the files to your repository and add a description message:
      git commit -m "new doctest for round()"
10) git push git@github.com:TeroFrondelius/julia.git
11) At your repository (https://github.com/TeroFrondelius/julia), create a pull request


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

### Bugs
+ http://doodlingindata.com/2014/12/29/documenting-julia-code/
+ https://github.com/JuliaLang/julia/issues/8965#issuecomment-67745941

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
+ https://github.com/JuliaLang/julia/issues/3701
+ https://github.com/JuliaLang/julia/issues/4774
+ https://github.com/JuliaLang/julia/pull/7568
+ https://github.com/JuliaLang/julia/pull/10525
+ https://groups.google.com/forum/#!topic/julia-dev/sM0VyVbFewQ

----

# Lib INDEX
+ Index : http://julia.readthedocs.org/en/latest/genindex/
+ http://julia.readthedocs.org/en/latest/stdlib/base/
+ http://stackoverflow.com/questions/25716547/type-i-discrete-cosine-transform-not-defined-found-in-julia-0-3-0

----

# Syntax
+ http://julia.readthedocs.org/en/latest/manual/noteworthy-differences/
+ http://docs.julialang.org/en/latest/manual/integers-and-floating-point-numbers/
+ Abstract types: http://julia.readthedocs.org/en/latest/manual/types/#abstract-types
+ Punctuation, http://julia.readthedocs.org/en/latest/stdlib/punctuation/
+ Metaprogramming, http://julia.readthedocs.org/en/latest/manual/metaprogramming/
+ Arguments of mathematical operators to a common type, https://julia.readthedocs.org/en/latest/manual/conversion-and-promotion/

### Bugs
+ Make `any` and `all` short-circuit, https://github.com/JuliaLang/julia/pull/11774


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

# NEWS
+ http://www.r-bloggers.com/an-r-programmer-looks-at-julia/
+ http://www.project1.com/expertise/data-science-analytics/data-science-report/item/2526-http-strataoreillycom-2012-10-matlab-r-julia-languages-for-data-analysishtml#.VcdFGaPLdOo
+ http://julialang.org/images/nyhackr.pdf

