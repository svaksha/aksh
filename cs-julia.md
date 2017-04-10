+ [0-5-DEV](#0-5-dev)
+ [CORE](#core)
   + [Daemons](#daemons)##
   + [Syntax-Symbols-Operators](#syntax-symbols-operators)
+ [Development](#development)
   + [dotjuliarc](#dotjuliarc)
   + [dotjulia](#dotjulia)
   + [GIST](#gist)
   + [Plotting](#plotting)
+ [Packaging](#packaging)
    + [build.jl](#build.jl)
    + [USING](#using)
    + [INCLUDE](#include)
+ [DOCUMENTATION](#documentation)
+ [QA](#qa)
    + [dottravis-yml](#dottravis-yml)
+ [MATH](#math)
   + [Arrays](#arrays)
   + [Calculus](#calculus)+ How do you tie t
   + [Graphs](#graphs)
   + [Algorithms](#algorithms)
+ [NEWS](#news)
+ [Web](#web)
+ [Shell](#shell)

----

+ Julia instance, https://tmpnb.org/user-tMmHkibTA4kf/tree
+ https://github.com/JuliaLang/julia/blob/master/CONTRIBUTING.md
   + https://github.com/IainNZ/ContributeToJulia
+ https://github.com/JuliaLang/julia/issues?q=is%3Aopen+is%3Aissue+label%3A%22up+for+grabs%22
+ 9493 : https://github.com/JuliaLang/julia/issues/9493
+ 5840 : https://github.com/JuliaLang/julia/issues/5840
* https://groups.google.com/forum/#!topic/julia-users/O5S8pPav5Ks
* https://www.cs.princeton.edu/~appel/papers/memerr.pdf
* http://homepages.mcs.vuw.ac.nz/~alex/files/MuscheviciPotaninTemperoNobleOOPSLA2008.pdf
* http://www.cs.cmu.edu/~neelk/focusing-on-pattern-matching.pdf

# Julia
http://code.metager.de/source/xref/julia/Graphs.jl/src/graph.jl
http://julialang.org/Graphs.jl/index.html
http://stackoverflow.com/search?page=1&tab=relevance&q=julia%20graph&s=2208559a-4c1a-4a0d-8fab-0f873299b3e1
http://stackoverflow.com/questions/23977361/create-simple-graph-object-in-julia-using-graphs-j
http://stackoverflow.com/questions/24578430/changing-vertices-value-with-graphs-jl
https://graphsjl-docs.readthedocs.org/en/latest/interface.html
http://julialang.org/Graphs.jl/matrix.html#weight-matrix
https://www.codecademy.com/forum_questions/4fc9081cb48d4c0003008395
http://www.chrisvoncsefalvay.com/2015/08/11/writing-good-julia-functions/
http://www.codegithub.com/watch?v=CSSJqqQQgUqU
https://plot.ly/julia/
http://samuelcolvin.github.io/JuliaByExample/
https://gist.github.com/gizmaa/7214002#axisplacement   ...plot
http://heike.github.io/stat590f/gadfly/andee-graphics/#/6
Dia



today()
strftime(time())
strftime("%F", time())
@time  
@elapsed

----


# 0-5-DEV

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

### BR
+ #7941:Towards array nirvana, https://github.com/JuliaLang/julia/issues/7941
+ https://github.com/JuliaLang/julia/issues/9874#issuecomment-75979041
+ https://github.com/JuliaLang/julia/issues/3701
+ https://github.com/JuliaLang/julia/issues/4774
+ https://github.com/JuliaLang/julia/pull/7568
+ https://github.com/JuliaLang/julia/pull/10525
+ https://groups.google.com/forum/#!topic/julia-dev/sM0VyVbFewQ
+ https://github.com/JuliaLang/julia/issues/7941
+ https://github.com/JuliaLang/julia/pull/10704

## Daemons
Fork a process or just `ccall fork`
+ https://github.com/JuliaLang/julia/issues/8295
+ https://github.com/JuliaLang/julia/issues/985#issuecomment-54837219

## Syntax-Symbols-Operators
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
+ Workflow tips: http://docs.julialang.org/en/release-0.4/manual/workflow-tips/
    + http://docs.julialang.org/en/latest/manual/workflow-tips/
+ __Month of Julia__ feed: http://www.juliabloggers.com/feed/
+ Index : http://julia.readthedocs.org/en/latest/genindex/
+ http://julia.readthedocs.org/en/latest/stdlib/base/
+ http://stackoverflow.com/questions/25716547/type-i-discrete-cosine-transform-not-defined-found-in-julia-0-3-0
+ API for scikit, https://github.com/svs14/Orchestra.jl/blob/master/src/python/scikit_learn.jl
+ JuliaStats-Roadmap.jl, https://github.com/JuliaStats/Roadmap.jl/issues/11

## JuliaComputing Roadmap
+ JuliaComputing Statistics roadmap: http://juliacomputing.com/blog/2016/01/14/stats-roadmap.html
+ julia-stats thread: https://groups.google.com/d/topic/julia-stats/29l5yA87Qss/discussion
Q1. Will the roadmap obviate some of the bottlenecks for day to day normal exploratory workflow?  These are minimal  things that R and Python have and whose lack hamper any use of Julia for regular analysis. Thing like robust dataframe with data i/o into different formats, web scraping, work out nullable semantics and integration with ecosystem , robust data cleaning and tidy data, modeling with basic  diagnostic tests etc

## dotjuliarc.jl
+ https://gist.github.com/Ismael-VC/6db0c310eaf04d0b0a1b
+ https://gist.github.com/search?l=julia&q=.juliarc.jl&ref=searchresults&utf8=%E2%9C%93
+ https://gist.github.com/ZacCranko/ac505c8db680ba97a9be
+ https://github.com/phobon/jconf/blob/c963dfbcd25372b341b4479d979416ad2f4167d2/julia/juliarc.jl
+ https://github.com/JuliaLang/julia/issues/5076
+ https://github.com/JuliaLang/julia/issues/6445
+ https://github.com/JuliaLang/julia/issues/10351 
+ https://github.com/JuliaLang/julia/issues/4222
+ https://books.google.de/books?id=P-09CgAAQBAJ&pg=PA91&lpg=PA91&dq=.juliarc+file&source=bl&ots=U6GC9cNQ8a&sig=ZjAhl9KqYHXxCbhJ9ZcKk4foJog&hl=en&sa=X&ved=0ahUKEwjluaXqhsPLAhXqCpoKHfyAALkQ6AEISDAH#v=onepage&q=.juliarc%20file&f=false

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

A cache. Other than that, no idea what it accomplishes (aside from reading the code to find out) or why it works the way it does. It was added in https://github.com/JuliaLang/julia/commit/df7a08893e4402182ec64178ffdb3130aa228943 but there are no design docs on the package manager. Ask Stefan. Also, `.cache` moved to being shared between different versioned package directories on 0.4 because of https://github.com/JuliaLang/julia/pull/7361. It worked that way on unix in 0.3 as well. With better support for making directory junctions via the symlink function (which was still a pretty new feature when 0.3.0 was released), that PR made the behavior consistent on Windows as well.

    
## Metaprogramming
+ How to use @eval, https://stackoverflow.com/questions/26071317/declaring-top-level-variables-in-julia-using-metaprogramming/26071597#26071597

## Macros
+ `import MyModule` will import package module on all workers (because @everywhere is redundant) which is @everywhere because if the module needs to be re-precompiled then it will be compiled only once. 

## GIST
+ cprintf.jl, https://gist.github.com/dpo/11000433

## Plotting
+ https://github.com/JuliaPlot/juliaplot_docs/issues/1
+ https://github.com/dcjones/Gadfly.jl/issues/658
+ https://github.com/tbreloff/Plots.jl/issues/30#issuecomment-142995667

## Working with Text Files
+ Working with paths and filenames: https://en.wikibooks.org/wiki/Introducing_Julia/Working_with_text_files#Working_with_paths_and_filenames

## Parallel Computing
+ http://www.csd.uwo.ca/~moreno/cs2101a_moreno/Parallel_computing_with_Julia.pdf

----

# Packaging
+ http://docs.julialang.org/en/latest/manual/packages/#package-development
+ http://julia.readthedocs.org/en/latest/stdlib/pkg/
+ http://docs.julialang.org/en/latest/manual/packages/
+ Old SO thread: http://stackoverflow.com/questions/14092316/simplest-ways-to-make-a-julia-package-available-to-others

+ To move a large number of packages installed on the old system to a new one, do `Pkg.init()`, then copy only the `REQUIRE` file from `~/.julia/v0.x/` folder, then do a `Pkg.update()` on the cli.
+ To ping a package to a version, the correct command is: `Pkg.checkout(pkg,branch)`. From, http://julia.readthedocs.org/en/latest/manual/packages/#checkout-pin-and-free
+ Set environment variable `JULIA_PKGDIR` for all users : http://docs.julialang.org/en/release-0.4/stdlib/pkg/#Base.Pkg.dir

### Naming and Coding Rules
+ Package naming rules, https://github.com/JuliaStats/Distributions.jl/issues/395
+ Coding rules, https://github.com/JuliaStats/Distributions.jl/issues/396


## build.jl
Good examples of various build files for dependencies: 
+ https://github.com/jiahao/GSL.jl/blob/master/deps/build.jl
+ https://github.com/JuliaLang/Cairo.jl/blob/master/deps/build.jl


## USING 
You can write `using A, B` to use both A and B but then you can't list specific 
bindings.
Example: 
´´´using A: fooA, barA
   using B: fooB, barB
´´´
__REQUIRE is deprecated, try using these: (include, reload, using, import)__
+ https://github.com/JuliaLang/METADATA.jl/issues/2777
+ Add to REQUIRE a package which isn't in METADATA, https://github.com/JuliaLang/julia/issues/7737
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

#### Deploying Julia libraries
On Wednesday, September 30, 2015 at 9:27:29 PM UTC-4, Sebastian Good wrote:

    Setting JULIA_PKGPATH lets me put everything in a more amenable spot, but transporting everything over to another identical machine results in inconsistent behavior with precompiled binaries. They are always “stale”. Is there a good resource to consult to understand binary staleness?

Staleness is determined by this function:

https://github.com/JuliaLang/julia/blob/e54c38d27028a0c79a10140c8271d484e182b295/base/loading.jl#L421-L449

In particular, it is considered stale if the absolute path changes, or if the modification time of a dependency (which is checked via the absolute path) does not match the modification time of the file when the cache was created.

So, a precompiled image will be considered stale if you change the absolute path of the cache or source directories.   It might be nice to make these relocatable without invalidating the cache.

However, in the meantime I don't think there is much downside to just having the user re-precompile the packages.  Precompilation is very different than building the package; it doesn't require internet access or other external resources, and re-running precompilation can basically only fail if importing the package fails, in which case you probably have bigger problems.

#### Anaconda Python, lewis-AT-neilson-levin discussion on JL binary distribution
I have built it all on Mac.  It really was quite terrible--put it all in a bash script and its worse yet on Windows--I tried and quickly went to WinPython or PythonXY in preference to Anaconda or ActiveState, both of which I also tried. I am glad that I don't have to any more. Haven't had to for about a year and a half.  Which is why we do want a decent approach to binary distribution. I agree that forking as a way to test innovation with an intention to eventually re-integrate is a fine way to make progress.  A permanent fork, on the other hand, seems undesirable though it happens for a variety of reasons.  

It appears that Python has stepped up to this, if belatedly and incompletely.  There are pre-built binaries available for Mac and Windows for numpy, matplotlib, scipy, and pandas provided by the maintainers of those packages.  These folks have stepped up and contributed a lot.  There are wheels for Mac and Windows for all of them--except Numpy on Windows.  In general, according to the scipy umbrella website, these binaries are targeted to the PSF binary distributions (2.7.10 and 3.5.0--with earlier versions available in many cases).  I am afraid that Linux is more challenging though in some cases the package repos for the major distros offer binaries though those are likely to lag. I think the recent breakage in some Python packages has occurred in the cycle of upgrading to work with Python 2.7.10 and 3.5.0.  Despite improvement it remains messy.

If Julia weren't so very good at integrating other things--Python, C, R, and using git as a package manager--we wouldn't be having the discussion.  We are having it because Julia's core team carefully invested where it should--in the defining innovations of the language--while finding very efficient ways to bootstrap some of the maintenance "machinery" and leveraging other platforms for needed capabilities.  The pace of progress, as a result, is simply astonishing for a language--really a nascent ecosystem--that has been here such a short time.

There are still issues managing large binary dependencies, but it must be done because having thousands of people build very large libraries doesn't make sense. I think Julia user-developers want to use the capabilities Julia provides without becoming sys admins.  Sounds like the Julia core team has some ideas for this, especially for statically compiled pure Julia packages (bring'em on!).  As to preferences for Python distributions, it seems a few things occasionally break when using PSF Python distro with pip managed packages.  It used to work; it will get sorted out.  Relying exclusively on a quasi-proprietary distro for the long-term doesn't seem like a good thing, though it has been expedient as an option and it is fine to have more than one option.  It makes sense for Julia to provide a self-contained Python for Julia users, especially for matplotlib/PyPlot.jl but also because it is so easy to use PyCall for lots of things.

I stirred up a rat's nest here and I am dropping it. In a way, this is more of an issue for the Python community than the Julia community.  Julia has adopted a new approach with more up to date and broadly adopted tooling (git--though the binary issue remains) which allows for much more rapid progress.  

#### How2create a stable version of Julia + other packages?

How to create a stable version of Julia + Gadfly + PyPlot + IJulia (+ other packages?) that prevents the students running `Pkg.add(...)/Pkg.update()`, as packages have a tendency to occasionally break on updates, and it's a headache dealing with this during the lecture. The possible solutions are:

1.  Prebake a .julia folder that contains all the necessary resources, with a script to reset in case the students break it with Pkg.update().
2.  Use system image: http://docs.julialang.org/en/release-0.4/devdocs/sysimg/, that includes all the necessary packages.   It's not really clear how to do this from the documentation, though.   I'm also not sure how that would interact with Pkg.update() though, so probably instructions to delete .julia would also need to be given.
3. https://github.com/rened/DeclarativePackages.jl, which allows you to run Julia with a given set of versions of given packages.
4. Possibly another option would be a Docker container image.

## Package Managers
+ http://dontkry.com/posts/code/modules-the-right-way.html

The Julia package manager lacks solutions to two problems that `npm` solves with nested dependencies inside the project folder:

1. The ability to have different versions of the same package active on the same machine, and even in the same project's (sub)dependencies.
2. The ability to specify dependencies and their versions on a per-project basis, also for projects that are not modules themselves, allowing you to check in a file specifying dependencies and then running something like `Pkg.restore()` to install everything you need.


## INCLUDE
+ The scope for `include("foo.jl")` is global scope only. You cannot call variables defined in different .jl file. See: 
http://docs.julialang.org/en/release-0.4/manual/noteworthy-differences/
+ The include statement should be used outside the function.
+ __Bug__, [relative using/import should search current directory](https://github.com/JuliaLang/julia/issues/4600)
+ With `importall` you dont need a submodule definition and can have a flat internal namespace.
+ Alternatively, write a macro in your module to do these for you in one line. Of course this may still include a file multiple times if you call include on it multiple times in the source file, however, for non-trivial inter-submodule dependency the python style submodule import.
+ Example: See https://github.com/eschnett/FunHPC.jl, where `src` has many files, each with its own module. The modules refer to each other, using regular "using" statements. In the tests folder, they are imported with `unshift!(LOAD_PATH, "../src")` so that statements such as `using Comm` find the respective module.
+ [Reexport](https://github.com/simonster/Reexport.jl) is another useful package.
+ For the locally defined A module (not a global A module), instead of modifying the LOAD_PATH, do this: 
'''
include("A.jl")
using .A
'''

----

# [DOCUMENTATION](http://docs.julialang.org/en/latest/manual/documentation/)
+ Documentation of Julia’s Internals, http://docs.julialang.org/en/latest/devdocs/julia/
+ Moving Docstrings, https://github.com/JuliaLang/julia/pull/12703
+ https://github.com/JuliaLang/julia/pull/11943
+ https://github.com/JuliaLang/julia/pull/11906
+ https://github.com/JuliaLang/julia/blob/ff9cebe45e6c39933ab26ca134b59b3ef47ec821/doc/helpdb.jl
+ Search for functions at the Julia REPL:
``` julia> apropos("standard deviation")
    randn!
    stdm
    std
    randn

    help?> std
    search: std stdm STDIN STDOUT STDERR setdiff setdiff! hist2d hist2d! stride strides StridedArray StridedVector StridedMatrix StridedVecOrMat redirect_stdin

      std(v[, region])

      Compute the sample standard deviation of a vector or array v, optionally along dimensions in region. The algorithm returns an estimator of the generative
      distribution's standard deviation under the assumption that each entry of v is an IID drawn from that generative distribution. This computation is equivalent to
      calculating sqrt(sum((v - mean(v)).^2) / (length(v) - 1)). Note: Julia does not ignore NaN values in the computation. For applications requiring the handling of
      missing data, the DataArray package is recommended.
```

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
+ http://www.stochasticlifestyle.com/finalizing-julia-package-documentation-testing-coverage-publishing/

## Code Coverage
+ Try, `Base.JLOptions().code_coverage`, (see https://github.com/JuliaLang/julia/blob/68b403f820fbd2f7401e12a90d487f41c96ca652/base/options.jl)
+ https://github.com/timholy/DebuggingUtilities.jl/commit/5f20ac4347f10687595cabaa2b304d073f7cf836

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

### dottravis.yml 

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
+ Math with Julia: https://www.reddit.com/r/Julia/comments/4zv7m1/what_is_a_learning_project/
+ mathematical abbreviations, https://en.wikipedia.org/wiki/List_of_mathematical_abbreviations
+ Numerical Analysis & Statistics: MATLAB, R, NumPy, Julia : http://hyperpolyglot.org/numerical-analysis

## Arrays

+ http://julia.readthedocs.org/en/latest/manual/arrays/
+ https://julia.readthedocs.org/en/latest/stdlib/arrays
+ http://quant-econ.net/jl/julia_arrays.html
+ http://en.wikibooks.org/wiki/Introducing_Julia/Arrays_and_tuples
+ Read .csv, http://randyzwitch.com/julia-import-data/
+ DF, https://github.com/JuliaStats/DataFrames.jl/blob/cac96119c9f5e24c5f2976ff119703a6ec52476c/src/abstractdataframe/abstractdataframe.jl#L67
+ https://stackoverflow.com/questions/24275980/slice-array-of-arrays-in-julia
+ Reshaped Arrays, https://github.com/JuliaLang/julia/pull/10507
+ Passing Objects, https://stackoverflow.com/questions/27677399/julia-how-to-copy-data-to-another-processor-in-julia

#### Array Division and Multiplication
    So..
    10 * [1:3]     is fine
    10 / [1:3]     is an error
    10 ^ [1:3]    also erroneous

+ Whereas multiplying a matrix by a scalar is well-defined in linear algebra, dividing by a matrix has a very specific meaning which requires a square matrix. Same with exponentiation. The dot-prefixed operators explicitly work elementwise, so use `.*`, `./` and `.^` for element-wise operations.


## Calculus
+ http://mth229.github.io/
+ http://docs.julialang.org/en/latest/stdlib/math/#numerical-integration
+ http://hwborchers.lima-city.de/JuliaMeetup/numerical/integration.html
+ http://stackoverflow.com/questions/29292614/how-to-do-two-variable-numeric-integration-in-julia
+ http://calculuswithjulia.github.io/precalc/functions.html
+ http://rosettacode.org/wiki/Numerical_integration/Gauss-Legendre_Quadrature
+ CUBATURE: https://cran.r-project.org/web/packages/cubature/cubature.pdf

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


## Statistics
+ http://www.juliabloggers.com/tag/normal-distribution/

#### etc..
http://julia.readthedocs.org/en/latest/stdlib/
http://bogumilkaminski.pl/files/julia_express.pdf
https://groups.google.com/forum/#!msg/julia-users/F4FQJMzbHsY/eRl7ZHl7KiIJ
http://quant-econ.net/jl/julia_libraries.html
https://github.com/stevengj/Cubature.jl/blob/master/src/Cubature.jl

----

# NEWS
+ Jeff Bezanson, Alan Edelman, Stefan Karpinski, and Viral B. Shah, Julia: A Fresh 
Approach to Numerical Computing, SIAM Rev., 59(1), 65–98. (34 pages), 
DOI:10.1137/141000671, 2017, Society for Industrial and Applied Mathematics
+ http://www.r-bloggers.com/an-r-programmer-looks-at-julia/
+ http://www.project1.com/expertise/data-science-analytics/data-science-report/item/2526-http-strataoreillycom-2012-10-matlab-r-julia-languages-for-data-analysishtml#.VcdFGaPLdOo
+ http://julialang.org/images/nyhackr.pdf

### Images
A new Images.jl has been tagged and it now uses FileIO for image loading and
saving. I've introduced FileIO in previous posts to this mailing list; it
improves the the ability to dynamically choose package(s) for image I/O.

One consequence is that by default, you may not have any installed image
loaders. If you're using Images interactively, FileIO will likely prompt you
to install appropriate package(s) as it discovers you need them.

However, this doesn't happen in "non-interactive" usage. So, if you maintain a
package whose tests depend on loading or saving images, I highly recommend
adding a test/REQUIRE file that specifies the package(s) you need for image I/O.
For example:

Contents of MyPkg/test/REQUIRE: ImageMagick

That should do the trick for the large majority of cases.


----


# Web 
+ Building a Web App in Julia for DifferentialEquations.jl,  http://www.juliabloggers.com/building-a-web-app-in-julia-differentialequations-jl-online/

---- 

# Shell
+ SSH cluster with Julia: http://kshyatt.github.io/2016/12/06/sshcluster.html
