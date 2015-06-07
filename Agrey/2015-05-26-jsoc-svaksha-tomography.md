+ [1. TOMOGRAPHY PROPOSAL](#1-tomography-proposal)
   + [Abstract](#abstract)
+ [2. ALGORITHM ONTOLOGY USECASE](#2-algorithm-ontology-usecase)
   + [Name](#name)
   + [Goal](#goal)
   + [Actors](#actors)
   + [Informal Description](#informal-description)
   + [Formal Description](#formal-description)
   + [Hypothesis of Application](#hypothesis-of-application)
        + [Example-1](#example-1)
+ [3. PROJECT SCOPE](#3-project-scope)
   + [3a. Implementation](#3a-implementation)
        + [Fourier Transform](#fourier-transform)
        + [Julia-FFTW](#julia-fftw)
   + [3b. Milestones](#3b-milestones)
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
   + [3c. Challenges]((#3c-challenges)
+ [4. MENTORS](#4-mentors)
   + [Logistics](#logistics)
+ [5. AboutMe](#5-aboutme)
+ [6. REFERENCES](#6-references)

----

# 1. TOMOGRAPHY PROPOSAL

### Abstract

Tomographic reconstruction creates three-dimensional (3D) views of an object by combining two-dimensional (2D) images taken from multiple directions, for example in how a computer-aided tomography (CAT) scanner allows 3D views of the heart or brain. The mathematical basis of tomography dates back to early nineties, when Johann Radon, an Austrian mathematician, developed a solution for the recovery of a 3D function from its line integrals [Radon, 1917]<sup>{0}</sup>. However, the engineering applications remain limited until the first CAT system became commercially available in early seventies. Since then its applications expanded tremendously, leading to landmark discoveries and breakthroughs in the fields of diagnostic medicine, as well as materials, earth and life sciences.

Synchrotron X-ray tomographic<sup>{1}</sup> microscopy (SRXTM) offers detailed three-dimensional scanning of an object, where numerous two-dimensional views of an object from multiple directioms are reconstructed computationally. Analysis of tomography synchrotron light source datasets requires efficient tools that can handle large datasets without compromising on speed, that integrate well with the existing codebase and are easy to maintain and add features. 

`TomoPy`<sup>{2}{3}</sup> is an open source, Python framework that is platform and data format independent, has multiprocessing capability and supports procedural programming that many researchers prefer<sup>{4}</sup>. At present, TomoPy utilizes compiled modules for demanding computations, making porting and distribution of the code more difficult. This project will create a new Radon transform<sup>{5}</sup> package library in Julia and implement that into the `TomoPy` Python framework. The result for this will be a more portable `TomoPy` implementation, will demonstrate the value of Julia to the scientific research community and likely attract more scientists to the Julia userbase. It will also provide a useful algebraic tool for other Julia users. 


# 2. ALGORITHM ONTOLOGY USECASE

## Name
Tomography.jl

## Goal
+ Implement the Radon transform algorithm, aka, filtered back projection (FBP), in Julia as a library that can be incorporated into the TomoPy<sup>{1}{2}</sup> toolbox to perform tomographic data processing and image reconstruction tasks at the Argonne Advanced Light Source (APS).

## Actors
+ TomoPy developers, 
+ Scientists using Tomography packages,
+ Scientists, software developers and other library users in the fields of seismic data processing, medical imaging, crystallography, radiology, plasma physics, materials science, astrophysics, and other sciences, 
+ Other algebraic computing users.

## Informal Description
+ A new package that implements the Radon transform algorithm in Julia.

## Formal Description
+ The Radon transform in two dimensions (2D) is a tomography method with applications in medical CT/CAT imaging systems, radiology, and other sciences for imaging by cross-sectional scans sections from the projection data through sine waves (sinograms). Correcting the noise corruption in projection data by using mathematical /geometry techniques will aid in image reconstruction.
+ TomoPy will be the glue interface layer, and the plan is to replace the C engine underneath with the Julia library for Radon transforms. 
+ The Julia Base code library will not be modified.

## Hypothesis of Application

Currently there is no library routine for this algorithm in Julia. Consequently, the system should provide the following capabilities, so lets consider a hypothetical application:

+ A user retrieves tomography data (from a patient, from a sample, etc.).
+ S/he applies several pre-processing routines (available in the TomoPy package) to clean the measurement data.
+ Then s/he applies the inverse Radon transform (i.e. image reconstruction algorithm) to recover volume images from data.
+ The output is stored in a file.

#### Example-1

```
using Base
#using function fourier_slice
num = 5
Y = 7
Z = [linspace(-num/2, num/2, num)]
println("Z= ",Z)
projection = exp(-num).^2
  println("projection= ", projection)
  @time projection
sinogram = fill(projection,Y,num)
  println("sinogram= ", sinogram)
  @time sinogram
resh = reshape ([sinogram], Y, num)
  println("resh =", resh)
angles = [linspace(0, pi, Y)]
  println("angles= ", angles)
```
__Output__

```
Z= [-2.5,-1.25,0.0,1.25,2.5]
projection= 4.539992976248485e-5
   4.129 microseconds (155 allocations: 10845 bytes)
sinogram= [4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5]
   1.111 microseconds (4 allocations: 144 bytes)
resh =[4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5
 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5 4.539992976248485e-5]
angles= [0.0,0.5235987755982988,1.0471975511965976,1.5707963267948966,2.0943951023931953,2.6179938779914944,3.141592653589793]
```
----

# 3. PROJECT SCOPE
This section contains the proposed scope, strategy vis-a-vis available Julia libraries, and challenges for completing the goals of this project with deliverables sliced into a weekly milestone timeline for the period between 2015Jun15 to 2015Sep15.

## 3a. Implementation

### Fourier Transform
The Radon transform is inversely related to the 2D Fourier transform<sup>{20}</sup> of the initial function, which is the one variable Fourier transform of the Radon transform<sup>{3}</sup> of that initial function. The Fourier transform is invertible on certain intervals of time resulting in an explicit inversion formula for the Radon transform.

### Julia-FFTW
Julia uses the FFTW<sup>{21}{22}</sup> library, the fastest free software implementation of the Fast Fourier transform (FFT) algorithm with support for multiple algorithms for smaller transforms, shared-memory parallelism, distributed-memory and multi-core support. However, while Julia supports shared-memory parallelism, it does not have support for all the features of FFTW so this will have to be considered during the implementation process.


## 3b. Milestones

The scheduled milestones are organised to be flexible so that some features are likely be completed early. Noted in the milestones are tasks including documentation and unit testing efforts for the features, with extended periods for reviewing these efforts at the two points during the project (halfway, final week). The milestones are:

### week01-2015jun15 
+ Implement the Radon transform algorithm - Start implementing the inverse Radon transform and linear system of equations for the back-projection algorithm using the NFFT.jl package.
+ Use the Julia ODE packages, [listed here](https://github.com/svaksha/Julia.jl/blob/master/Mathematics.md#ordinary-differential-equation), to implement the differential equations.

### week02-2015jun22 
+ Holiday: a 5 day trip that was planned before JSoC/JuliaCon was announced. To compensate for these 5 days, I plan to work over 2 or 3 weekends inorder to catchup.

### week03-2015jun29 
+ To implement a new Radon transform<sup>{3}</sup> package library describing the forward projection process (FBP).
+ Continue with the `iterative reconstruction` algorithms to reconstruct 2D and 3D images for tomography computations which are computationally more expensive than FBP.

### week04-2015jul06 
+ Run tests on the ongoing Radon transform (sine waves or sinogram) implementation for a crystallography image.

### week05-2015jul13 
+ Implement the inversion method using iterative algorithms.
+ The Algebraic Reconstruction Technique (ART) iteratively computes the inverse of the Radon transform in two dimensions.
+ Test it with the standard `Shepp–Logan phantom`<sup>{13}</sup> test image.

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
+ The parallel matrix-vector products and linear algebra operations for sparse distributed matrices will be handled via TomoPy, which is the glue interface layer that will be tested with the implementation of Radon Transform lib support in Julia. 

### week11-2015aug24
+ Code is refactored where necessary.
+ Create a Travis testing for CI and deployment from Julia.

### week12-2015aug31 
+ Code Reviews and refactoring. 

### week13-2015sep07 
+ The final week until 2015Sep15 is for more testing and finishing up with documentation writing.


## 3c. Challenges

This section is meant for internal discussion and tracking as I need to be aware of proposed (possibly breaking) changes to the Julia language Base/core that _may_ affect the codebase in future and keep my mentors informed of the same.

+ 3c-1. Currently Julia has breaking changes planned for arrays<sup>{7}{8}{9}{10}</sup> in version-0.5 and the last suggestion in the thread seemed to suggest that they may make backporting changes to array behavior via Compat feasible<sup>{11}</sup> but another dev thinks backporting features is a terrible idea as it can break packages between two versions released for the Julia language. Array/Matrix computation forms the bedrock of scientific computing so this is a big change and the main goal behind listing these challenges in my proposal is to get feedback from the Mentors on how these issues will affect the project proposal and how we can find a solution to work around it. 

+ 3c-2. Package precompilation<sup>{14}</sup> will probably make it into version-0.4 before the freeze, which should be a helpful feature for those users who, for security reasons, may not have access to an internet connection. Like Python, it is proposed to use __init__<sup>{15}</sup> for the syntax so that the package searches for the compiled (.jlc) file during installation but the long discussion for keeping it as an opt-in (to avoid breakage on old versions) is ongoing. Another change this will bring about in the packaging system will be with respect to _precompiled libs_ inside the julia packaging system, including the _module dependencies_ within a package. How these will be stored and handled is something to watch out for.

+ 3c-3. Continuing the abstract array<sup>{16}</sup> discussion, there is another bug tracker discussion over array concatenation<sup>{17}</sup> and I am wondering if (and how) this will affect the code written for Radon?

+ 3c-4. To check if TomoPy requires or uses any graphics and rendering libs? The 2014 GSoC produced 2D/3D rendering for graphics, and support for GUI/Visualization libraries also exists which will help increase the adoption of Julia for these tasks thanks to the speed boost from LLVM. 

----

# 4. MENTORS
1. Doga Gürsoy<sup>{1}</sup>, PhD, Assistant Computational Scientist, APS, Argonne National Laboratory; @dgursoy on Github.
2. Francesco De Carlo<sup>{1}</sup>, PhD, Scientific leader, APS, Argonne National Laboratory; @decarlof on Github.

I am in touch with the core developers of the TomoPy library who will mentor me with respect to the Tomography scientific programming. A Julia core-developer will be sought for helping with code reviews.

### Logistics
+ Communicate via emails and github issues.
+ Track progress via regular git commits, blog posts and weekly meetings, if required. 

----

# 5. AboutMe
I am Vidya.A, a computing technologist and FOSS contributor from India. My [bio page](http://svaksha.com/pages/Bio) describes my Foss journey so I'll try to avoid repetition and keep it short :- My interests lie in scientific programming and I have worked on a bioinformatics project and a financial project that used python scientific libraries which kindled a deeper interest in scientific programming. At present I am not a student but in future, I plan to pursue the graduate school option and work within a research team. The idea of introducing Julia into a scientific research codebase motivated me to apply for JSoC.

By creating an algebraic tool for Julia users, this project will go a long way in demonstrating the importance of Julia to the scientific research community, namely medical imaging, crystallography and radiology. I've been reading various research papers, the `tomopy` codebase and scientific material in preparation for this project inorder to understand the best implementation methods and have been having discussions with my mentors regarding the challenges involved - given the recent mailing list discussions involving breaking changes planned for arrays<sup>{7}{8}{9}{10}</sup> in version-0.5 and abstract array<sup>{16}</sup> and array concatenation<sup>{17}</sup>, package precompilation<sup>{14}</sup>, lib support for linear solvers and sparse matrices, data storage and processing.

Thusfar, Python has been the language of choice for all my projects, but there have been moments when I have looked for a better alternative, specifically in terms of the chaotic linux packaging ecosystem, speed, syntax (read, whitespace), etc.. where Julia scored highly. It is a new language in the scientific programming world, with a focus on numerical computing<sup>{18}</sup>, hence it has a huge amount of potential to replace established languages like Python in the scientific programming world. Hence, I'm hoping to contribute to some amazing libraries that can improve the adoption of Julia within the scientific community. That the language itself has amazing potential is evident in the exponential growth-rate of packages registered on Metadata, with almost triple of those listed on Julia.jl<sup>{19}</sup> (which I created in 2012 as a private wiki to track Julia code repos on github - then around 350-400). Most importantly, I like the helpful community around Julia and believe that a package used in the Tomography imaging field will be of great value to the scientific research community and help rope in more scientists to the Julia userbase. 

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
+ {10} https://github.com/JuliaLang/julia/pull/10525
+ {11} https://groups.google.com/forum/#!topic/julia-dev/sM0VyVbFewQ
+ {12} http://en.wikipedia.org/wiki/Iterative_reconstruction
+ {13} http://en.wikipedia.org/wiki/Shepp%E2%80%93Logan_phantom
+ {14} https://github.com/JuliaLang/julia/pull/8745
+ {15} http://docs.julialang.org/en/latest/manual/modules/?highlight=__init__#module-initialization-and-precompilation
+ {16} https://github.com/JuliaLang/julia/blob/master/base/abstractarray.jl
+ {17} https://github.com/JuliaLang/julia/issues/10338
+ {18} Paper: [Julia: A Fresh Approach to Numerical Computing](http://arxiv.org/abs/1411.1607) by Jeff Bezanson, Alan Edelman, Stefan Karpinski, Viral B. Shah.
+ {19} http://svaksha.github.io/Julia.jl
+ {20} https://en.wikipedia.org/wiki/Fourier_transform
+ {21} https://en.wikipedia.org/wiki/FFTW
+ {22} https://github.com/FFTW/fftw3

