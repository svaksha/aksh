

# Debug a package
using BinDeps, PkgName
BinDeps.debug("PkgName")

----

# QA - core JULIA
+ https://github.com/JuliaLang/julia/blob/master/test/unicode.jl
+ https://github.com/JuliaLang/julia/blob/e0176ec9c44530f4474f2f347613de121f9ed1fc/test/pkg.jl

## Unit and Functional Testing
+ http://julia.readthedocs.org/en/latest/stdlib/test/

----

# Packaging
+ http://docs.julialang.org/en/latest/manual/packages/#package-development
+ http://julia.readthedocs.org/en/latest/stdlib/pkg/
+ http://docs.julialang.org/en/latest/manual/packages/
+ Old SO thread: http://stackoverflow.com/questions/14092316/simplest-ways-to-make-a-julia-package-available-to-others

To move a large number of packages installed on the old system to a new one, do `Pkg.init()`, then copy only the `REQUIRE` file from `~/.julia/v0.x/` folder, then do a `Pkg.update()` on the cli.

### Naming and Coding Rules
+ Package naming rules, https://github.com/JuliaStats/Distributions.jl/issues/395
+ Coding rules, https://github.com/JuliaStats/Distributions.jl/issues/396

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

# ANN: Testing specific Julia versions on Travis CI
__Important DEV Notes from Tony__

Hey folks, an announcement for package authors and users who care about testing:

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

