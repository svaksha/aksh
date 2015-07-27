+ [Why Julia?](#why-julia?)
+ [ONE](#one)
+ [TWO](#two)
+ [CONSTRAINTS](#constraints)
+ [BIBLIOGRAPHY](#bibliography)

---- 

# Why Julia?

Before delving further, a few words on why I chose Julia, a language for technical computing. Avoiding Java, JS and other front-end web scripting languages was intentional - one, being a research lab, I assume researching and experimenting with new languages on the block is expected of researchers. Secondly, with the advent of DataScience and large-scale cloud computing, I forsee a huge potential for scientific programming inorder to handle large volumes of big data in the backend, where JS/Java are hardly used in number crunching and technical computing. Here, a language like Julia has the potential to give other languages currently used on production systems for scientific (like Matlab, R, Python, C/C++, Fortran) and backend (like Scala, Go, C++, Java, etc..) programming some tough competition in terms of language speed[3], new syntax features[4], libraries[5], etc..

Julia is a new language in the scientific programming world, with a focus on numerical computing[0], hence it has a huge amount of potential overtake older established languages like Python. The latter is often panned for being slow and having too many dependencies (think numpy, scipy, et al). The Julia language is easy to install (via git), has a built-in package manager (METADATA), has been designed for parallelism and distributed computation, Unicode support, support for LLVM and JIT compilation, coroutines and threads, supports object-oriented, functional, procedural, generic, reflective programming with multiple dispatch, a dynamic type system, meta, scalar and array-oriented, parallel, concurrent, distributed ("cloud") features. 

Programmers can directly call Python functions (via PyCall), including functions written in other programming languages[1] like C/C++, Erlang, Fortran, Go, Java, JavaScript, MATLAB, ObjectiveC, Perl, R and Ruby.

In its dynamic type system, the type expression [2] is implicit with optional explicit typing

Julia intends to assimilate the best from R, MATLAB, C++ and Python into one language that is fast, consistent and well-designed. Perhaps the hopeful thought that Julia language will become one of the top scientific programming language tool in the near future seems naive today (and might stem from my lack of perspective on all the CS paradigms and programming languages that form a body of already published research) but I am hoping that collective insight, knowledge and experience will help guide the way forward. 

[3] Besides the language speed, the rate of language development is very fast-paced even between 0-point releases - a lot of v0.4 bug-fix changes will make some parts of v0.3 obsolete, not to forget some syntax changes.
[4] For example, python requires numpy (hence cython) for hard-core array-based programming whereas this feature is inbuilt in Julia.
[5] Things are in a state of flux as julia (master on git) keeps changing between 0-point releases. Despite Julia not being stable enough for a "production" server (at the time of writing this), the core should be quite stable by the time it crosses v0.5 in a few months thanks to the fast-paced development rate and quick turn-around on bug fixes.
[0] Paper: [Julia: A Fresh Approach to Numerical Computing](http://arxiv.org/abs/1411.1607) by Jeff Bezanson, Alan Edelman, Stefan Karpinski, Viral B. Shah
[1] https://github.com/svaksha/Julia.jl/blob/master/API.md#languages
[2] http://julia.readthedocs.org/en/latest/manual/types/

---- 

# ONE (Uninitialized variable in Julia).

How would an uninitialized variable in Julia conflict between performance and safety{5} and how would it be resolved - in favor of performance? or safety? What would be consequences of the trade off? These are some research aspects that I would like to investigate. 

In the discussion thread and the bug report [6, 7], it was suggested that zero's be added to an uninitialized array[6], but this approach (inserting zero's in a large array) would be slow and error-prone for tabulations on multiple composite types when we have a large array. Variable initialization is expensive in terms of speed and the Julia core-developers think only pure data types like Int or Float64[7] if left uninitialized will pose a problem. 

[6] https://groups.google.com/forum/#!topic/julia-users/O5S8pPav5Ks
[7] https://github.com/JuliaLang/julia/issues/9147

So is it reasonable not to initialize variables? What happens when in 99% of the cases the array will be filled anyway with values that are actually computed using other data or by another routine that calls this class? Imagine another scenario, where we use a particular routine repeatedly - here, each time the routine executes, it is is allocated memory space and upon completion (of execution) the memory will (should) be cleared. There exists a possibility that the allocated memory cache may not get cleaned, resulting in it continuing to store the old (redundant) data values. 

In this scenario, when my program is run repeatedly (assuming a time span between runs) the program will pick up the junk values resulting in unpredictable or wrong computation. From the database perspective, would the data replication[8] feature providing redundancy and high availability allow me to ensure data precision in scientific calculations? How would the replication of junk data degrade the performance and reliability of data for tasks that need to ensure data precision? For scientific computation (like DNA sequence alignment, Astronomy, financial trading, etc..) this can have potential negative results. Hypothetically, this can also (at minimal worst case) be a security issue in conjunction with poor client-side implementation of UI/UX.

[8] http://docs.mongodb.org/manual/replication/


### Database 

Will the choice of the Database have an impact on the safety and reliability of data when I use an uninitialised variable? Not initializing storage can be hazardous when I consider the "programming task" and "what kind of data" I am creating (or storing) which in turn influences the "type of database" being used. For example, how would the safety performance be affected when one stores data in an RDBMS datastore (say, Postgres) VS. a NoSQL database (say, MongoDB or Redis) VS. an array DB (like SciDB) VS. a graph DB (like Neo4J). I would speculate that each scientific computation (like DNA sequence alignment, Astronomy, financial trading, etc..) task would require or use a different kind of DB, depending on what their end goal is. 

Data replication is a common strategy to store and back-up data, besides it being available on demand
.

  With uninitialized storage, a 
      program may run fine one day, and fail mysteriously the next, depending on 
      the contents of memory.  This is about predictability, reliability, dependability,
      and correctness.

   -- I would favor a solution like
             A = Array(Int64,n)                   -- fills with zeros
             A = Array(Int64,n,fill=1)          -- to fill with ones
             A = Array(Int64,n,fill=None)    -- for an uninitialized array
       so that the *default* is an initialized array, but the speed geeks
       can get what they want.
       
       
I guess part of the problem is that calling the `zeros` function may be less obvious as a way of constructing an array to many new programmers than calling the `Array` constructor. Having a Boolean fill keyword argument approach might be reasonable, although calling it `zeroed` might be more accurate since we won't be filling the array with a specific value but rather zeroing the memory first. Alternatively, we could just fill the array with random garbage intentionally so that programmers are made painfully aware that they didn't initialize the array


You can call Java, meaning the JVM. Would it be impossible reuse Java code without the JVM or the other way to compile Julia (a executable or the whole environment) to Java (or CLR)? Is a C2Java available/possible? As Julia2C (and f2c) is available and assuming C2Java, couldn't Julia run in the JVM? Or in JavaScript (see Emscripten C2JavaScript compiler).

---- 

# TWO (Integer Overflow Checking)
* [The Performance Cost of Integer Overflow Checking](http://danluu.com/integer-overflow/)


# CONSTRAINTS

My proposal is constrained by some limitations due to the fact that I dont have access to powerful highly-scalable hardware. My laptop currently runs Ubuntu-14.04-LTS with 2GB RAM which drastically limits the amount of experiments that I can perform with large data files and this directly impacts what I can propose after actually testing out certain code.

---- 

# BIBLIOGRAPHY
* https://www.cs.princeton.edu/~appel/papers/memerr.pdf
* [Automatic Testing of Sequential and Concurrent Substitutability](http://mp.binaervarianz.de/icse2013.pdf), Michael Pradel, Thomas R. Gross, [Code](http://mp.binaervarianz.de/icse2013/)

### Bib : Multiple dispatch, pattern matching, etc..
* http://homepages.mcs.vuw.ac.nz/~alex/files/MuscheviciPotaninTemperoNobleOOPSLA2008.pdf
* http://www.cs.cmu.edu/~neelk/focusing-on-pattern-matching.pdf

