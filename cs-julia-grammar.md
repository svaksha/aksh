+ [Functional](#functional)
+ [Include](#include)
+ [Macros](#macros)
+ [MAP](#map)
+ [OOP](#oop)
+ [RANGES](#ranges)

----

# Functional
+ An intro to functional programming: http://www.bootstrapworld.org/materials/ 

----

# Include
+ The scope for `include("foo.jl")` is global scope only. You cannot call variables defined in different .jl file. See: 
http://docs.julialang.org/en/release-0.4/manual/noteworthy-differences/
+ The include statement should be used outside the function.

----

# Macros
### @everywhere
@everywhere id = myid() 
remotecall_fetch(2, ()->id)  # The @everywhere macro executes a statement on all running processes.

----

# MAP
__map-broadcast__

+ Alternative syntax for `map(func, x)` : https://github.com/JuliaLang/julia/issues/8450

----

# OOP

Julia is not an OOP language.

### Inheritance
https://groups.google.com/forum/#!topic/julia-dev/eA4VkFAD-yQ
 
### Looping Vs. OOP in Julia

One doesn't always need to write the loops oneself. Oftentimes switching from a pure operator (e.g. broadcast) to its in-place counterpart (e.g. broadcast!) can make a world of difference:

julia> A = rand(5_000_000);

julia> function f(A)
    sum(A .+ A.^2)
end
f (generic function with 1 method)

julia> f(A); @time f(A)
0.182246 seconds (206 allocations: 76.307 MB, 5.70% gc time)
4.166856979458311e6


julia> _g(x, y) = x + y^2
_g (generic function with 1 method)

julia> function g(A)
    temp = Array(Float64,5_000_000)
    broadcast!(_g, temp, A, A)
    sum(temp)
end
g (generic function with 1 method)

julia> g(A); @time g(A)
0.023660 seconds (8 allocations: 38.147 MB, 28.73% gc time)
4.166856979458311e6

Thus it may help to cultivate knowledgeable use of map! and broadcast! as opposed to pure broadcasted operators 

----

# RANGES

1) Why are there so many Range types? There is a UnitRange (start, stop),  a StepRange (start, step, stop), and a FloatRange(start, step, length, divisor), but I don't really understand why you can't just use the StepRange for everything. Maybe I'm just missing some obvious use cases, but this seems to lead to inconsistent or confusing behaviour like the 1 in my second question.

2) `findin` seems to have inconsistent behaviour for ranges depending on types in the ranges. `findin(::UnitRange, ::UnitRange)` returns another UnitRange, but `findin(::StepRange, ::StepRange)` returns an array of the indices. Is there some reason that these shouldn't be consistent?

Ex:
```
julia> findin(1:10, 2:5)
2:5

julia> findin(1:1:10, 2:2:5)
2-element Array{Int64,1}:
 2
 4

julia> r1 = DateTime(now())-Dates.Day(60):DateTime(now())
2015-08-22T19:07:47:1 day:2015-10-21T19:07:47

julia> r2 = r1[1:20]
2015-08-22T19:07:47:1 day:2015-09-10T19:07:47

#### Reply

> I don't really understand why you can't just use the StepRange for everything

You could. However, you can be more efficient by having special types (e.g. with UnitRange you don't need to check the steps).

>  `findin(::UnitRange, ::UnitRange)` returns another UnitRange

This seems good.

> `findin(::StepRange, ::StepRange)` returns an array of the indices

You might be able to do some maths here to return a StepRange... at least for Integers:

function Base.findin{T <: Integer}(a::StepRange{T}, b::StepRange{T})
    start = ??
    step = b.step ÷ gcd(a.step, b.step)
    stop = max(a.stop, b.stop)
    start:step:stop
end

but I 'm not sure this is possible with floats...

Looking in the source mentioning UnitRange here's a more serious bug: https://github.com/JuliaLang/julia/blob/e16c6784e1ba6f24b6faf0d282c78d8c14a1fbb3/base/array.jl#L866


julia> findin([5.2, 3.3], 3:20)
2-element Array{Int64,1}:
 1
 2

julia> findin([5.2, 3.3], 3:1:20)
0-element Array{Int64,1}

----

