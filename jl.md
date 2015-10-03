+ [0.4-dev](#0.4-dev)
+ [CORE](#core)
   + [Syntax-Symbols-Operators](#syntax-symbols-operators)
+ [Development](#development)
   + [.juliarc](#.juliarc)
   + [GIST](#gist)
   + [IJulia](#ijulia)
   + [Plotting](#plotting)
+ [Packaging](#packaging)
    + [USING](#using)
+ [Documentation](#documentation)
+ [QA](#qa)
    + [.travis.yml](#.travis.yml)
+ [MATH](#math)
   + [Arrays](#arrays)
   + [Graphs](#graphs)
   + [Algorithms](#algorithms)
+ [NEWS](#news)

----

+ Julia instance, https://tmpnb.org/user-tMmHkibTA4kf/tree
+ https://github.com/JuliaLang/julia/blob/master/CONTRIBUTING.md
   + https://github.com/IainNZ/ContributeToJulia
+ https://github.com/JuliaLang/julia/issues?q=is%3Aopen+is%3Aissue+label%3A%22up+for+grabs%22
+ 9493 : https://github.com/JuliaLang/julia/issues/9493
+ 5840 : https://github.com/JuliaLang/julia/issues/5840
   
----

# 0.4-dev

+ Freeze : https://github.com/JuliaLang/julia/blob/master/NEWS.md#julia-v040-release-notes

✶ Troubleshoot errors when running the unstable DEV branch

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

# CORE
+ http://docs.julialang.org/en/latest/#developer-documentation

## BR
+ #7941:Towards array nirvana, https://github.com/JuliaLang/julia/issues/7941
+ https://github.com/JuliaLang/julia/issues/9874#issuecomment-75979041
+ https://github.com/JuliaLang/julia/issues/3701
+ https://github.com/JuliaLang/julia/issues/4774
+ https://github.com/JuliaLang/julia/pull/7568
+ https://github.com/JuliaLang/julia/pull/10525
+ https://groups.google.com/forum/#!topic/julia-dev/sM0VyVbFewQ
+ https://github.com/JuliaLang/julia/issues/7941
+ https://github.com/JuliaLang/julia/pull/10704

### Syntax-Symbols-Operators
+ http://julia.readthedocs.org/en/latest/manual/noteworthy-differences/
+ http://docs.julialang.org/en/latest/manual/integers-and-floating-point-numbers/
+ Abstract types: http://julia.readthedocs.org/en/latest/manual/types/#abstract-types
+ Punctuation, http://julia.readthedocs.org/en/latest/stdlib/punctuation/
    + julia-parser.scm: https://github.com/JuliaLang/julia/blob/master/src/julia-parser.scm#L3-L23
    + https://julia.readthedocs.org/en/latest/stdlib/punctuation/
    + http://docs.julialang.org/en/release-0.4/manual/functions/?highlight=anonymous#anonymous-functions
+ Metaprogramming, http://julia.readthedocs.org/en/latest/manual/metaprogramming/
+ Arguments of mathematical operators to a common type, https://julia.readthedocs.org/en/latest/manual/conversion-and-promotion/


### Advice
+ Make `any` and `all` short-circuit, https://github.com/JuliaLang/julia/pull/11774
+ Deprecation warning flags : `empty!(Base.have_warned)`

### Conditionals
+ http://slendermeans.org/julia-iterators.html
+ http://julia.readthedocs.org/en/latest/manual/control-flow/#man-loops   
+ https://en.wikibooks.org/wiki/Introducing_Julia/Controlling_the_flow

### RE Strings
+ http://julia.readthedocs.org/en/latest/stdlib/strings/
+ http://julia.readthedocs.org/en/latest/manual/strings/ 
+ https://stackoverflow.com/questions/20478823/joining-regular-expressions-in-julia

### Discussion: Multiple dispatch vs Single Dispatch syntax
For starters, what something should belong to is not always unambiguous - viz. should a function that splits string a at every occurrence of b be a.split(b) or b.split(a)? None of the solutions is inherently significantly better than the other. 

More importantly, search in Julia does not belong to either "Hello World" or e. It belongs to the current namespace. In OOP languages, x.f(y) is the combination of two things: f being under the namespace of x, and f being defined as f(self, y). self is then substituted with x, and so it effectively devolves to f(x, y). Classes are used as proxy namespaces, so that search would be held in the namespace of the string classed object "Hello World" in your example. The benefit of that is that you know where to look for the function. In Julia, there's an overarching namespace. There is an expense associated with that, which is why OOP languages do what they do. But just by changing how we express f(x, y) to x.f(y) or y.f(x) actually doesn't change any of that. Nothing short of actually implementing a full-blown class system with behaviours that properly 'belong to' classes does. Which is not what the design decision was when Julia was started. As such, while I like the syntactic simplification involved here, I just can't see how it would be either trivial but useless or useful but subverting some fundamental underlying design decisions.

### JuliaWeb
+ https://github.com/JuliaWeb/Roadmap/issues

### Linear Algebra 
+ https://github.com/JuliaLang/julia/issues?q=is%3Aopen+label%3A%22up+for+grabs%22+is%3Aissue+label%3A%22linear+algebra%22
+ #4668 [Proposal: Better linear algebra benchmarks](https://github.com/JuliaLang/julia/issues/4668)

----

# Development
+ __Month of Julia__ feed: http://www.juliabloggers.com/feed/
+ Index : http://julia.readthedocs.org/en/latest/genindex/
+ http://julia.readthedocs.org/en/latest/stdlib/base/
+ http://stackoverflow.com/questions/25716547/type-i-discrete-cosine-transform-not-defined-found-in-julia-0-3-0
+ API for scikit, https://github.com/svs14/Orchestra.jl/blob/master/src/python/scikit_learn.jl
+ JuliaStats-Roadmap.jl, https://github.com/JuliaStats/Roadmap.jl/issues/11

## .juliarc.jl
+ https://github.com/JuliaLang/julia/issues/5076
+ https://github.com/JuliaLang/julia/issues/6445
+ https://github.com/JuliaLang/julia/issues/10351 
+ https://github.com/JuliaLang/julia/issues/4222

## ~/.julia
+ Notes on basing development repos in ~/.julia and doing development and commits from there with recommended setup/process for creating packages using Pkg to manage them.
   + Develop packages in their own directories on the user filesystem: `./julia/<package>/` 
   + From there, in `./src/`, keep the various source files.  One, specifically is called "nomodule.jl".  This contains a `require(<types.jl>)` and `"include(<functions.jl>)`
   + For each code change, do a `reload("nomodule.jl`) from the REPL.  This replaces all functions, except for the type definitions which can't be updated.
   + To change the types, do a `ctrl-D; julia; reload("nomodule.jl")` which can be a bit of a pain.
   + When happy with the functionality, make this code into a module, using a file "<Module>.jl", very similar to the "nomodule.jl" but with the "require" replaced by "include".
   + Then, sync this with github.
   + If you need the functionality from another working directory, do a `Pkg.clone(<github>)` to load a sort-of-stable version into ~/.julia
   + Then, do a pull request to METADATA.jl for your package to be included in the standard set of Julia packages. 
   + For functionality on some other machines, sync using git, either through github or directly.

### What is the .cache directory and why was it moved into the ~\.julia folder for 0.4?

A cache. Other than that, no idea what it accomplishes (aside from reading the code to find out) or why it works the way it does. It was added in https://github.com/JuliaLang/julia/commit/df7a08893e4402182ec64178ffdb3130aa228943 but there are no design docs on the package manager. Ask Stefan.

.cache moved to being shared between different versioned package directories on 0.4 because of https://github.com/JuliaLang/julia/pull/7361. It worked that way on unix in 0.3 as well. With better support for making directory junctions via the symlink function (which was still a pretty new feature when 0.3.0 was released), that PR made the behavior consistent on Windows as well.

    
## Metaprogramming
+ How to use @eval, https://stackoverflow.com/questions/26071317/declaring-top-level-variables-in-julia-using-metaprogramming/26071597#26071597

## GIST
+ cprintf.jl, https://gist.github.com/dpo/11000433

## IJulia
+ Proper method for including external JS libraries?, https://github.com/JuliaLang/IJulia.jl/issues/345
+ IJulia Errors "load failed, save is disabled" in 0.5-dev despite making the notebook "trusted" : https://github.com/JuliaLang/IJulia.jl/issues/252

## Plotting
+ https://github.com/JuliaPlot/juliaplot_docs/issues/1
+ https://github.com/dcjones/Gadfly.jl/issues/658
+ https://github.com/tbreloff/Plots.jl/issues/30#issuecomment-142995667

----

# Packaging
+ http://docs.julialang.org/en/latest/manual/packages/#package-development
+ http://julia.readthedocs.org/en/latest/stdlib/pkg/
+ http://docs.julialang.org/en/latest/manual/packages/
+ Old SO thread: http://stackoverflow.com/questions/14092316/simplest-ways-to-make-a-julia-package-available-to-others

+ To move a large number of packages installed on the old system to a new one, do `Pkg.init()`, then copy only the `REQUIRE` file from `~/.julia/v0.x/` folder, then do a `Pkg.update()` on the cli.
+ To ping a package to a version, the correct command is: `Pkg.checkout(pkg,branch)`. From, http://julia.readthedocs.org/en/latest/manual/packages/#checkout-pin-and-free

### Naming and Coding Rules
+ Package naming rules, https://github.com/JuliaStats/Distributions.jl/issues/395
+ Coding rules, https://github.com/JuliaStats/Distributions.jl/issues/396

## USING
__REQUIRE is deprecated__
+ https://github.com/JuliaLang/METADATA.jl/issues/2777
+ add to REQUIRE a package which isn't in METADATA, https://github.com/JuliaLang/julia/issues/7737
+ https://github.com/JuliaLang/METADATA.jl/issues/2800
+ https://github.com/rened/DeclarativePackages.jl

### Using VS. import VS. importall
+ https://julia.readthedocs.org/en/latest/manual/modules/
+ https://github.com/JuliaLang/julia/issues/11031 
+ https://github.com/JuliaLang/julia/issues/8000
+ Only make exported bindings available with `import`, https://github.com/JuliaLang/julia/issues/12069
+ https://en.wikibooks.org/wiki/Introducing_Julia/Modules_and_packages


From Leah:
I think his summary in #11031 is accurate, and the reason given directly in the reply is the reason for using/importall to be different. Issue #8000 is a discussion of ways to change/simplify the syntax.

I'll take a stab at rephrasing the different in case that helps. There is only one difference, and on the surface (syntax-wise) it may seem very minor. The difference between "using" and "importall" is that with "using" you need to say "function Foo.bar(.." to extend module Foo's function bar with a new method, but with "importall" or "import Foo.bar", you only need to say "function bar(..." and it automatically extends module Foo's function bar.

If you use "importall", then "function Foo.bar(..." and "function bar(..." become equivalent. If you use "using", then they are different.

The reason this is important enough to have been given separate syntax is that you don't want to accidentally extend a function that you didn't know existed, because that could easily cause a bug. This is most likely to happen with a method that takes a common type like string or int, because both you and the other module could define a method to handle such a common type. If you use importall, then you'll replace the other module's implementation of "bar(s::String)" with your new implementation, which could easily do something complete different (and break all/many future usages of the other functions in module Foo that depend on calling bar).


### BR
+ Rewrite Pkg.add to include repo argument [BUG # 11914](https://github.com/JuliaLang/julia/issues/11914).

### Binaries
+ Conda.jl, https://github.com/JuliaLang/METADATA.jl/pull/3238
+ build.jl, https://github.com/JuliaOpt/Ipopt.jl/blob/99b85463ca408aefb4931d2ebaaa97cf5f821acc/deps/build.jl#L42-L45

### Deploying Julia libraries
On Wednesday, September 30, 2015 at 9:27:29 PM UTC-4, Sebastian Good wrote:

    Setting JULIA_PKGPATH lets me put everything in a more amenable spot, but transporting everything over to another identical machine results in inconsistent behavior with precompiled binaries. They are always “stale”. Is there a good resource to consult to understand binary staleness?
>
Staleness is determined by this function:

https://github.com/JuliaLang/julia/blob/e54c38d27028a0c79a10140c8271d484e182b295/base/loading.jl#L421-L449

In particular, it is considered stale if the absolute path changes, or if the modification time of a dependency (which is checked via the absolute path) does not match the modification time of the file when the cache was created.

So, a precompiled image will be considered stale if you change the absolute path of the cache or source directories.   It might be nice to make these relocatable without invalidating the cache.

However, in the meantime I don't think there is much downside to just having the user re-precompile the packages.  Precompilation is very different than building the package; it doesn't require internet access or other external resources, and re-running precompilation can basically only fail if importing the package fails, in which case you probably have bigger problems.

----

# Documentation
+ Documentation of Julia’s Internals, http://docs.julialang.org/en/latest/devdocs/julia/
+ Moving Docstrings, https://github.com/JuliaLang/julia/pull/12703
+ https://github.com/JuliaLang/julia/pull/11943
+ https://github.com/JuliaLang/julia/pull/11906
+ https://github.com/JuliaLang/julia/blob/ff9cebe45e6c39933ab26ca134b59b3ef47ec821/doc/helpdb.jl

### HowTo write help text in a function that could be displayed with `?`
+ REPL, `julia> Docs.@repl sin`
`search: sin sinh sind sinc sinpi asin using isinf asinh asind isinteger`
+ Then, in the REPL `julia> @doc sin`, where `sin(x)` ==  Compute sine of x, where x is in radians

 
    
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

### BR
+ http://doodlingindata.com/2014/12/29/documenting-julia-code/
+ https://github.com/JuliaLang/julia/issues/8965#issuecomment-67745941

----

# QA

## Code Coverage
+ Try, `Base.JLOptions().code_coverage`, (see https://github.com/JuliaLang/julia/blob/68b403f820fbd2f7401e12a90d487f41c96ca652/base/options.jl)

## Debug a package
using BinDeps, PkgName
BinDeps.debug("PkgName")

## QA - core JULIA
+ https://github.com/JuliaLang/julia/blob/master/test/unicode.jl
+ https://github.com/JuliaLang/julia/blob/e0176ec9c44530f4474f2f347613de121f9ed1fc/test/pkg.jl


### ANN: Testing specific Julia versions on Travis CI
__Important DEV Notes from Tony__

✶ Hey folks, an announcement for package authors and users who care about testing:

We've had support for Julia package testing on Travis CI for almost 9 months now, ref https://groups.google.com/forum/#!msg/julia-users/BtCxh4k9hZA/ngUvxdxOxQ8J if you missed the original announcement. Up to this point we supported the following settings for which Julia version to test against:

    language: julia
    julia:
        - release
        - nightly

Release has meant the latest release version in the 0.3.x series, and nightly has meant the latest nightly build of 0.4-dev master. Once Julia 0.4.0 gets released, the meaning of these settings will change, where release will be the latest version in the 0.4.x series, and nightly will be the latest nightly build of 0.5-dev master. Considering the wide install base and number of packages that may want to continue supporting 0.3 even after 0.4.0 gets released, we've just added support for additional version options in your .travis.yml file. You can now do

    julia: 
        - release
        - nightly
        - 0.3

Or, if you want to test with specific point releases, you can do that too (there should not usually be much need for this, but it could be useful once in a while to compare different point releases):

    julia: 
        - release
        - nightly
        - 0.3
        - 0.3.10

The oldest point release for which we have generic Linux binaries available is 0.3.1. If you enable multi-os support for your repository (see http://docs.travis-ci.com/user/multi-os/), then you can go back as far as 0.2.0 on OS X. Note that you'd need to replace the default test script with the old-fashioned `julia test/runtests.jl` since `Pkg.test` and `--check-bounds=yes` are not supported on Julia version 0.2.x. The downloads of those versions would fail on Linux workers so you may need to set up a build matrix with excluded jobs (see http://docs.travis-ci.com/user/customizing-the-build/#Build-Matrix).

### Unit and Functional Testing
+ http://julia.readthedocs.org/en/latest/stdlib/test/

### .travis.yml 

I've noticed many people with .travis.yml files that perhaps no longer mean quite what people think they do.

In particular:

language: julia
julia:
  - release
  - nightly

Currently means "Test on Julia 0.3.11 and Julia 0.5-dev"
When Julia 0.4.0 comes out, it'll mean "Test on Julia 0.4.0 and Julia 0.5-dev"

My preference has been to make it precise, so either

language: julia
julia:
  - 0.3
  - 0.4
  - nightly

If you want to try to support all 3 versions, or

language: julia
julia:
  - 0.3
  - 0.4

If you just want to support the stable versions, or

language: julia
julia:
  - 0.4
  - nightly

If you want to give up on 0.3 (which is fine, just make sure you update your REQUIRE file!)


----

# MATH

+ mathematical abbreviations, https://en.wikipedia.org/wiki/List_of_mathematical_abbreviations

## Arrays

+ http://julia.readthedocs.org/en/latest/manual/arrays/
+ https://julia.readthedocs.org/en/latest/stdlib/arrays
+ http://quant-econ.net/jl/julia_arrays.html
+ http://en.wikibooks.org/wiki/Introducing_Julia/Arrays_and_tuples
+ Read .csv, http://randyzwitch.com/julia-import-data/
+ DF, https://github.com/JuliaStats/DataFrames.jl/blob/cac96119c9f5e24c5f2976ff119703a6ec52476c/src/abstractdataframe/abstractdataframe.jl#L67
+ https://stackoverflow.com/questions/24275980/slice-array-of-arrays-in-julia
+ Reshaped Arrays: https://github.com/JuliaLang/julia/pull/10507

#### Array Division and Multiplication
    So..
    10 * [1:3]     is fine
    10 / [1:3]     is an error
    10 ^ [1:3]    also erroneous

+ Whereas multiplying a matrix by a scalar is well-defined in linear algebra, dividing by a matrix has a very specific meaning which requires the a square matrix.  Same with exponentiation.  The dot-prefixed operators explicitly work elementwise, so use `.*`, `./` and `.^` for element-wise operations.


## Integral
+ http://docs.julialang.org/en/latest/stdlib/math/#numerical-integration
+ http://hwborchers.lima-city.de/JuliaMeetup/numerical/integration.html
+ http://stackoverflow.com/questions/29292614/how-to-do-two-variable-numeric-integration-in-julia
+ http://calculuswithjulia.github.io/precalc/functions.html
+ http://rosettacode.org/wiki/Numerical_integration/Gauss-Legendre_Quadrature

## Algorithms
+ Strassen algorithm for matrix multiplication in julia: https://gist.github.com/GaZ3ll3/87df748f76b119199fed
   + Jupyter NB: http://nbviewer.ipython.org/github/GaZ3ll3/Step_In_Julia/blob/master/notebook/Linear%20Algebra.ipynb


## Graphs
+ https://github.com/JuliaGraphs/LightGraphs.jl
+ http://julialang.org/Graphs.jl/index.html
+ https://graphsjl-docs.readthedocs.org/en/latest/interface.html
+ https://graphsjl-docs.readthedocs.org/en/latest/vertex_edge.html 
+ http://julialang.org/Graphs.jl/matrix.html#adjacency_matrix

+ https://stackoverflow.com/questions/26071317/declaring-top-level-variables-in-julia-using-metaprogramming/26071597#26071597
+ https://stackoverflow.com/questions/24578430/changing-vertices-value-with-graphs-jl?rq=1
+ https://stackoverflow.com/questions/23480722/what-is-a-symbol-in-julia?rq=1
+ https://gist.github.com/ohadle/11323991
+ https://github.com/JuliaLang/Graphs.jl/issues/171

#### etc..
http://julia.readthedocs.org/en/latest/stdlib/
http://bogumilkaminski.pl/files/julia_express.pdf
https://groups.google.com/forum/#!msg/julia-users/F4FQJMzbHsY/eRl7ZHl7KiIJ
http://quant-econ.net/jl/julia_libraries.html
https://github.com/stevengj/Cubature.jl/blob/master/src/Cubature.jl

----


# NEWS
+ http://www.r-bloggers.com/an-r-programmer-looks-at-julia/
+ http://www.project1.com/expertise/data-science-analytics/data-science-report/item/2526-http-strataoreillycom-2012-10-matlab-r-julia-languages-for-data-analysishtml#.VcdFGaPLdOo
+ http://julialang.org/images/nyhackr.pdf

----

