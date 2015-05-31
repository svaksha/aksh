+ [1. TOMOGRAPHY PROPOSAL](#1-tomography-proposal)
   + [Abstract](#abstract)
+ [2. USECASE](#2-usecase)
+ [3. PROJECT SCHEDULE](#2-project-schedule)
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
+ [4. MENTORS](#3-mentors)
   + [Logistics](#logistics)
+ [5. AboutMe](#4-aboutme)
+ [6. REFERENCES](#6-references)
+ [7. Challenges & Queries](#5-challenges-&-queries)

----

# 1. TOMOGRAPHY PROPOSAL

### Abstract

Tomographic reconstruction creates three-dimensional (3D) views of an object by combining two-dimensional (2D) images taken from multiple directions, for example in how a computer-aided tomography (CAT) scanner allows 3D views of the heart or brain. The mathematical basis of tomography dates back to early nineties, when Johann Radon, an Austrian mathematician, developed a solution for the recovery of a 3D function from its line integrals [Radon, 1917]<sup>{0}</sup>. However, the engineering applications remain limited until the first CAT system became commercially available in early seventies. Since then its applications expand tremendously, leading to landmark discoveries and breakthroughs in the fields of diagnostic medicine, as well as materials, earth and life sciences.

Synchrotron X-ray tomographic<sup>{1}</sup> microscopy (SRXTM) offers detailed three-dimensional scanning of an object, where numerous two-dimensional views of an object from multiple directioms are reconstructed computationally. Analysis of tomography synchrotron light source datasets requires efficient tools that can handle large datasets without compromising on speed, that integrate well with the existing codebase and are easy to maintain and add features. 

`TomoPy`<sup>{2}{3}</sup> is an open source, Python framework that is platform and data format independent, has multiprocessing capability and supports procedural programming that many researchers prefer<sup>{4}</sup>. At present, TomoPy utilizes compiled modules for demanding computations, making porting and distribution of the code more difficult. This project will create a new Radon transform<sup>{5}</sup> package library in Julia and implement that into the `TomoPy` Python framework. The result for this will be a more portable `TomoPy` implementation, will demonstrate the value of Julia to the scientific research community and likely attract more scientists to the Julia userbase. It will also provide a useful algebraic tool for other Julia users. 


# 2. USECASE

### Goal
+ Implement the filtered back projection (FBP), aka, dual Radon transform algorithm in Julia as a library that can be incorporated into the TomoPy<sup>{1}{2}</sup> toolbox to perform tomographic data processing and image reconstruction tasks at the Argonne Advanced Light Source (APS).

### Actors
+ TomoPy developers, 
+ Scientists using Tomography packages,
+ Scientists, software developers and other library users in the fields of seismic data processing, radiology, plasma physics, materials science, astrophysics, and other sciences, 
+ Other algebraic computing users.

### Scope
+ The Julia Base code library will not be modified, rather, this project involves creating a new package. 

### Level
+ TomoPy will stay as a glue interface layer, but the plan is to replace the C engine underneath with the Julia library for Radon transforms. 

### Story
+ The Radon transform in two dimensions (2D) is a tomography method with applications in medical CT/CAT imaging systems, radiology, and other sciences for imaging by cross-sectional scans sections from the projection data through sine waves. Correcting the noise corruption in projection data by using mathematical /geometry techniques will aid in image reconstruction.

----

# 3. PROJECT SCHEDULE

This section contains the proposed strategy for completing this project with deliverables sliced into a weekly milestone timeline for the period between 2015Jun15 to 2015Sep15.

## Milestones
These scheduled milestones are organised to be flexible, which means that some features will likely be completed early. Noted in the milestones are tasks including documentation and unit testing efforts for the features, with extended periods for reviewing these efforts at the two points during the project (halfway, final week). The milestones are:

### week01-2015jun15 
+ Implement the Radon transform algorithm.
+ Start implementing the inverse Radon transform and linear system of equations for the back-projection algorithm.
+ To implement a new Radon transform<sup>{3}</sup> package library describing the forward projection process (FBP).

### week02-2015jun22 
+ Holiday: a 5 day trip that was planned before JSoC/JuliaCon was announced. To compensate for these 5 days, I plan to work over 2 or 3 weekends inorder to catchup.

### week03-2015jun29 
+ Continue with the `iterative reconstruction` algorithms to reconstruct 2D and 3D images for tomography computations which are computationally more expensive than FBP.

### week04-2015jul06 
+ Implement the Radon transform (sine waves or sinogram) of a crystallography image.

### week05-2015jul13 
+ Implement the inversion method using iterative algorithms.
+ The Algebraic Reconstruction Technique (ART) iteratively computes the inverse of the Radon transform in two dimensions.
+ Test it with the standard `Shepp–Logan phantom`<sup>{12}</sup> test image.

### week06-2015jul20 
+ Compute the slice-wise 3D inverse of the radon transform using multiprocessing.
+ Write tests and docs.

### week07-2015jul27 
+ Generate 3D variants of the 2D sinogram inversion methods using multiprocessing.
+ Write tests and docs.

### week08-2015aug03 
+ Evaluate algorithms with small test data. 
+ Contingency for tasks expected to arise from work reviews.

### week09-2015aug10 
+ Metadata package - creation of a meta package which can be called via PyCall or an API.
+ More tests and documentation.

### week10-2015aug17
+ Check the radon tomography package with the DICOM<sup>{6}</sup> interface library format for reading .dcm files.

### week11-2015aug24
+ Code is refactored where necessary.

### week12-2015aug31 
+ Code Reviews and refactoring. 

### week13-2015sep07 
+ The final week until 2015Sep15 is for more testing and finishing up with documentation writing.

----

# 4. MENTORS
1. Doga Gürsoy<sup>{1}</sup>, PhD, Assistant Computational Scientist, APS, Argonne National Laboratory; @dgursoy on Github.
2. Francesco De Carlo<sup>{1}</sup>, PhD, Scientific leader, APS, Argonne National Laboratory; @decarlof on Github.

I am in touch with the core developers of the TomoPy library who will mentor me with respect to tomography scientific programming. A Julia core-developer will be sought for helping with code reviews.

### Logistics
+ Communicate via emails and github issues.
+ Track progress via regular git commits, blog posts and weekly meetings, if required. 

----

# 5. AboutMe
I am Vidya.A, a computing technologist and FOSS contributor from India. My [bio page](http://svaksha.com/pages/Bio) describes my Foss journey so I'll try to avoid repetition and keep it short: My interests lie in scientific programming and I have worked on a bioinformatics project and a financial project that used python scientific libraries which kindled a deeper interest in scientific programming. At present I am not a student but in future, I plan to pursue the graduate school option and work within a research team. The idea of introducing Julia into a scientific research codebase motivated me to apply for JSoC.

By creating an algebraic tool for Julia users, this project will go a long way in demonstrating the importance of Julia to the scientific research community, namely medical imaging, crystallography and radiology. I've been reading various research papers, the `tomopy` codebase and scientific material in preparation for this project inorder to understand the best implementation methods and have been having discussions with my mentors regarding the challenges involved - given the recent mailing list discussions involving breaking changes planned for arrays<sup>{7}{8}{9}</sup> in version-0.5 and abstract array<sup>{15}</sup> and array concatenation<sup>{16}</sup>, package precompilation<sup>{13}</sup>, lib support for linear solvers and sparse matrices, data storage and processing.

Thusfar, Python has been the language of choice for all my projects, but there have been moments when I have looked for a better alternative, specifically in terms of the chaotic linux packaging ecosystem, speed, syntax (read, whitespace), etc.. where Julia scored highly. Hence, I'm hoping to contribute to some amazing libraries that can improve the adoption of Julia within the scientific community. Most importantly, I like the helpful community around Julia, and the language itself has amazing potential as is evident in the exponential growth-rate of packages registered on Metadata, with almost triple of those listed on Julia.jl (which I created in 2012 as a private wiki to track Julia packages on github - then around 350-400). I believe a Crystallography package will be of great value to the scientific research community and help in bringing more scientists to the Julia userbase. 

+ Contact details: http://svaksha.com/pages/Contact
+ Your online persona: http://svaksha.com/ (blog)

----

# 6. REFERENCES
+ {0} https://ieeexplore.ieee.org/xpl/articleDetails.jsp?arnumber=4307775
+ {1} https://www1.aps.anl.gov/Science/Scientific-Software/TomoPy
+ {2} https://github.com/tomopy/tomopy
+ {3} http://en.wikipedia.org/wiki/Radon_transform
+ {4} http://scripts.iucr.org/cgi-bin/paper?S1600577514013939
+ {5} https://en.wikipedia.org/wiki/Tomography
+ {6} https://github.com/ihnorton/DICOM.jl
+ {7} https://github.com/JuliaLang/julia/issues/3701
+ {8} https://github.com/JuliaLang/julia/issues/4774
+ {9} https://github.com/JuliaLang/julia/pull/7568
+ {10} https://groups.google.com/forum/#!topic/julia-dev/sM0VyVbFewQ
+ {11} http://en.wikipedia.org/wiki/Iterative_reconstruction
+ {12} http://en.wikipedia.org/wiki/Shepp%E2%80%93Logan_phantom
+ {13} https://github.com/JuliaLang/julia/pull/8745
+ {14} http://docs.julialang.org/en/latest/manual/modules/?highlight=__init__#module-initialization-and-precompilation
+ {15} https://github.com/JuliaLang/julia/blob/master/base/abstractarray.jl
+ {16} https://github.com/JuliaLang/julia/issues/10338

---- 

# 7. Challenges & Queries

This section of the proposal is for internal discussion and not all of it will make it into the final proposal to be submitted to JSoC. The idea is to be aware of proposed (possibly breaking) changes to the language core that _may_ affect the codebase in future.

+ 5.1. Currently Julia has breaking changes planned for arrays<sup>{7}{8}{9}</sup> in version-0.5 and the last suggestion in the thread seemed to suggest that they may make backporting changes to array behavior via Compat feasible<sup>{10}</sup> but another dev thinks backporting features is a terrible idea as it can break packages between two versions released for the Julia language. Array/Matrix computation forms the bedrock of scientific computing so this is a big change and the main goal behind listing these challenges in my proposal is to get feedback from the Mentors on how these issues will affect the project proposal and how we can find a solution to work around it. 

+ 5.2. Package precompilation<sup>{13}</sup> will probably make it into version-0.4 before the freeze, which should be a helpful feature for those users who for security reasons may not have access to an internet connection. Like python, it is proposed to use __init__<sup>{14}</sup> for the syntax so that the package searches for the compiled (.jlc) file during installation but the long discussion for keeping it as an opt-in (to avoid breakage on old versions) is ongoing. Another change this will bring about in the packaging system will be with respect to _precompiled libs_ inside the julia packaging system, including the _module dependencies_ within a package. How these will be stored and handled is something to watch out for.

+ 5.3. Radon transform falls under the category of "Integral geometry (transforms)" and "Linear operators" but I am not sure if it requires Geometric integrators and Sparse distributed matrices. Will the implementation of Radon Transform require lib support in Julia for parallel matrix-vector products and linear algebra operations for sparse distributed matrices? <= These don't exist right now, so I would like your advice on this aspect.
 
+ 5.4. I assume any data (matrix) pulled off a single image will be a very big array but since I dont have access to your work environment, I am not sure how to quantify it, how the processing will be done, how the data is stored, etc.. How will I be able to test the code and how will this code be used, as in, do you plan to integrate it within the TomoPy codebase or do you prefer to keep it as a distinct Julia library that can be called via PyCall? Mostly that is how Julia packages work and if it is an independent package, it can be used by biologists/chemists too. Once I get your advise on this I can modify the proposal accordingly.

+ 5.5. Continuing the abstract array<sup>{15}</sup> discussion, there is another bug tracker discussion over array concatenation<sup>{16}</sup> and I am wondering if (and how) this will affect the code written for Radon?
 
----
 
# QUESTIONS 
     

As a side note the current impementation uses Conda for packaging and distributions, and Travis for CI. What is the progress on CI and deployment from Julia side (or I should say from Tra 
