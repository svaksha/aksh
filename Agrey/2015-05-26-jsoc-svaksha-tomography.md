+ [1. TOMOGRAPHY PROPOSAL](#1-tomography-proposal)
   + [Abstract](#abstract)
   + [UseCase](#usecase)
+ [2. PROJECT SCHEDULE](#2-project-schedule)
   + [Milestones](#milestones)
        + [week01-2015jun15](#week01-2015jun15)
        + [week02-2015jun22](#week02-2015jun22)
        + [week03-2015jun29](#week03-2015jun29)
        + [week04-2015jul06](#week04-2015jul06)
        + [week05-2015jul13](#week05-2015jul13)
        + [week06-2015jul20](#week06-2015jul20)
        + [week07-2015jul27](#week07-2015jul27)
        + [week08-2015aug03](#week08-2015aug03) 
        + [week09-2015aug10](#week09-2015aug10)
        + [week10-2015aug17](#week10-2015aug17)
        + [week11-2015aug24](#week11-2015aug24)
        + [week12-2015aug31](#week12-2015aug31) 
        + [week13-2015sep07](#week13-2015sep07)
+ [3. MENTORS](#3-mentors)
   + [Logistics](#logistics)
+ [4. AboutMe](#4-aboutme)
+ [5. Challenges](#5-challenges)
+ [6. References](#6-references)

----

# 1. TOMOGRAPHY PROPOSAL

### Abstract

Computational analysis of tomography synchrotron light source datasets requires efficient tools that can handle large datasets without compromising on speed, integrates well with the existing codebase and is easy to maintain and add features. TomoPy<sup>{0}{1}</sup> is an open source, Python framework that is platform and data format independent, has multiprocessing capability and supports procedural programming that many researchers prefer<sup>{3}</sup>.

This proposal aims to create a new Radon transform<sup>{2}</sup> package library to complement the existing python framework 

Synchrotron X-ray tomographic<sup>{4}</sup> microscopy (SRXTM) allows for detailed three-dimensional scanning of an object.


The Julia Base code library will not be modified, rather, this project involves creating a new Radon transform<sup>{2}</sup> package library that can replace the C code functionality in Tomopy.


### UseCase
+ __Goal__: Implement the filtered back projection (FBP), aka, dual Radon transform algorithm in Julia for the TomoPy<sup>{0}</sup> library toolbox to perform tomographic data processing and image reconstruction tasks at the APS, ANL.

+ __Primary Actor__:
+ __Scope__:
+ __Level__:
+ __Story__: the body of the use case is simply a paragraph or two of text, informally describing what happens.

----

# 2. PROJECT SCHEDULE

This section contains the proposed strategy for completing this project with weekly milestones and deliverables.

## Milestones
These scheduled milestones are organised to be flexible, which means that some features will likely be done early. Also, the weeks include documentation and unit testing efforts for the features, with extended periods for reviewing these efforts at the two points during the project (halfway, final week). The milestone timeline for the project, between 2015Jun15 to 2015Sep15, is as below:

### week01-2015jun15 
+ Implement Radon transform algorithm
+ Start implementing the inverse Radon transform and linear system of equations for the back-projection algorithm.
+ To implement a new Radon transform<sup>{2}</sup> package library describing the forward projection process.

### week02-2015jun22 
+ Holiday: a 5 day trip that was planned before JSoC or JuliaCon was announced. To compensate for these 5 days, I plan to work over 2 or 3 weekends inorder to catchup.

### week03-2015jun29 
+ Continue with the `iterative reconstruction` algorithms to reconstruct 2D and 3D images for tomography computations. 
+ They are computationally more expensive than FBP.

### week04-2015jul06 
+ DICOM.jl
+ Check the radon tomography package with the DICOM<sup>{5}</sup> interface library format for reading .dcm files.
   

### week05-2015jul13 
+ Implement the inversion method using iterative algorithms.
+ The Algebraic Reconstruction Technique (ART) iteratively computes the inverse of the Radon transform in two dimensions.
+ Test it with the standard `Shepp–Logan phantom`<sup>{11}</sup> test image.

### week06-2015jul20 
+ 

### week07-2015jul27 

### week08-2015aug03 

### week09-2015aug10 
+ Metadata package - creation of a meta package which can be called via PyCall or an API.

### week10-2015aug17
+ Test the code from Week09.

### week11-2015aug24
+ Code is refactored where necessary.

### week12-2015aug31 
+ Code Reviews and refactoring. 

### week13-2015sep07 
+ [] The final week until 2015Sep15 is for more testing and finishing up with documentation writing.

----

# 3. MENTORS

1. Doga Gürsoy<sup>{0}</sup>, PhD, Assistant Computational Scientist, APS, Argonne National Laboratory; @dgursoy on Github.
2. Francesco De Carlo<sup>{0}</sup>, PhD, Scientific leader, APS, Argonne National Laboratory; @decarlof on Github.

I am in touch with the above mentioned core developers of the Tomography library who will mentor me with respect to tomography scientific programming. As yet, I have not sought out any Julia core-developers but it would be nice if a Julia developer were interested in helping out with code reviews, especially with guidance regarding speed and code optimization.

### Logistics

+ Track progress via regular git commits, blog posts and weekly meetings, if required. 
+ It is illegal to work without proper work authorization, so I would not want to do anything illegal. Relocating outside my country to work on a paid project like JSoC without a legal work permit seems illegal.

----

# 4. AboutMe

I'm Vidya.A, a computing technologist and FOSS contributor from India. My [bio page](http://svaksha.com/pages/Bio) describes my Foss journey so I'll try to avoid repetition and keep it short: My interests lie in scientific programming and I have worked on a bioinformatics project and a financial project that used python scientific libraries which kindled a deeper interest in Science per se. 

Python was the language of choice for all my projects thusfar, but there have been some moments when I have looked for a better alternative, specifically in terms of the packaging ecosystem, speed, syntax, etc.. areas in which Julia scored higher. Hence, I'm hoping to contribute to some amazing libraries that can improve the adoption of Julia within the scientific community. Most importantly, I like the helpful community around Julia, and the language itself has amazing potential as is evident in the exponential growth-rate of packages registered on Metadata, with almost triple of those listed on Julia.jl, which started life on a private wiki that I was using to track Julia packages on github - around 350-400 when I started in 2013. 

+ Contact details: http://svaksha.com/pages/Contact
+ Your online persona: http://svaksha.com/ (blog)

----

# 5. Challenges

+ 5.1. Currently Julia has breaking changes planned for arrays<sup>{6}{7}{8}</sup> in version-0.5 and the last suggestion in the thread seemed to suggest that they may make backporting changes to array behavior via Compat feasible<sup>{9}</sup> but another dev thinks backporting features is a terrible idea as it can break packages between two versions released for the Julia language. Array/Matrix computation forms the bedrock of scientific computing so this is a big change and the main goal behind listing these challenges in the proposal is to get feedback from the Mentors on how these issues will affect the project proposal and how we can find a solution to work around it. 

+ 5.2. 


----
 
# 6. References
+ {0} https://www1.aps.anl.gov/Science/Scientific-Software/TomoPy
+ {1} https://github.com/tomopy/tomopy
+ {2} http://en.wikipedia.org/wiki/Radon_transform
+ {3} http://scripts.iucr.org/cgi-bin/paper?S1600577514013939
+ {4} https://en.wikipedia.org/wiki/Tomography
+ {5} https://github.com/ihnorton/DICOM.jl
+ {6} https://github.com/JuliaLang/julia/issues/3701
+ {7} https://github.com/JuliaLang/julia/issues/4774
+ {8} https://github.com/JuliaLang/julia/pull/7568
+ {9} https://groups.google.com/forum/#!topic/julia-dev/sM0VyVbFewQ
+ {10} http://en.wikipedia.org/wiki/Iterative_reconstruction
+ {11} http://en.wikipedia.org/wiki/Shepp%E2%80%93Logan_phantom

