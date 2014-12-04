* [ONE](#one)
* [TWO](#two)
* [CONSTRAINTS](#constraints)
* [BIBLIOGRAPHY](#bibliography)

---- 

# ONE (Uninitialized variable in Julia).

How would an uninitialized variable in Julia conflict between performance and safety and how would it be resolved - in favor of performance? or safety? What would be consequences of the trade off? These are some research aspects that I would like to investigate. 

### Why Julia?

Julia is a new language in the scientific programming world, yet has a huge amount of potential overtake established languages like Python. The latter is often panned for being slow and having too many dependencies (think numpy, scipy, et al).

Avoiding Java, JS and other front-end web scripting languages was intentional - one, this being a research lab, I assume it is open to researching and experimenting with new languages on the block, and secondly, with the advent of DataScience and cloud computing I forsee a huge potential for scientific programming and technical computing that handle large volumes of big data in the backend, where JS/Java are hardly used. Here, a language like Julia has the potential to give other backend programming languages (like Scala, Go, Python, Fortran, Perl, etc..) that are currently used on production systems, some tough competition in terms of speed[1], new syntax features[2], libraries[3], etc..

[1] Besides the language speed, the rate of language development is very fast-paced even between 0-point releases - a lot of v0.4 changes will make some parts of v0.3 obsolete, not to forget some syntax changes.
[2] For example, python requires numpy (hence cython) for hardcore array-based programming whereas this feature is inbuilt in Julia.
[3] In a state of flux as julia (master on git) keeps changing between releases, but given the fast-paced development rate, the core should be quite stable by the time it crosses v0.5 in a few months.

---- 

# CONSTRAINTS

My proposal is constrained by some limitations due to the fact that I dont have access to powerful highly-scalable hardware. My laptop currently runs Ubuntu-14.04-LTS with 2GB RAM which drastically limits the amount of experiments that I can perform with large data files and this directly impacts what I can propose after actually testing out certain code.

---- 

# BIBLIOGRAPHY
* https://www.cs.princeton.edu/~appel/papers/memerr.pdf

### Bib : Multiple dispatch, pattern matching, etc..
* http://homepages.mcs.vuw.ac.nz/~alex/files/MuscheviciPotaninTemperoNobleOOPSLA2008.pdf
* http://www.cs.cmu.edu/~neelk/focusing-on-pattern-matching.pdf

