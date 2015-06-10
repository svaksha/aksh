+ [Tomography](#tomography)
   + [Radon Transform](#radon-transform)
   + [FFT](#fft)
+ [PHANTOM](#phantom)
+ [FOSS](#foss)
+ [PUBLICATIONS](#publications)
   + [Papers](#papers)
   + [Books](#books)

----

+ [CV](http://en.wikipedia.org/wiki/Computer_vision) and [Medical Imaging](http://en.wikipedia.org/wiki/Category:Medical_imaging)
+ Doppler effect Redshift: http://en.wikipedia.org/wiki/Redshift

# Tomography
+ https://en.wikipedia.org/wiki/X-ray_computed_tomography
+ https://en.wikipedia.org/wiki/Tomography
+ http://en.wikipedia.org/wiki/Medical_imaging#Conventional_tomography

## Radon Transform
+ [Radon transform](http://en.wikipedia.org/wiki/Radon_transform) and its complex analog is the [Penrose transform](http://en.wikipedia.org/wiki/Penrose_transform).
+ http://mathworld.wolfram.com/RadonTransform.html
+ MATHWORKS Radon transform, http://www.mathworks.com/help/images/ref/radon.html
+ Matlab’s image registration toolbox: http://www.mathworks.com/discovery/image-registration.html 
+ Slides on Radon transform, https://graphics.ethz.ch/teaching/viscomp11/downloads/VisComp07a_Radon_v02.pdf
+ [The Radon and Fourier Transforms: The mathematics of X-Rays and CT scans](http://www.math.ucla.edu/~heilman/papers/04172010Radon.pdf).
+ http://matlab.izmiran.ru/help/toolbox/images/transf12.html
+ http://matlab.izmiran.ru/help/toolbox/images/transfo8.html and http://matlab.izmiran.ru/help/toolbox/images/transfo9.html

## FFT 
+ [FFT](http://en.wikipedia.org/wiki/Fast_Fourier_transform) and [Discrete Fourier Transform](https://en.wikipedia.org/wiki/Discrete_Fourier_transform).
+ FIT, https://en.wikipedia.org/wiki/Fourier_inversion_theorem
+ Jake's FFT [Notebook](http://nbviewer.ipython.org/url/jakevdp.github.io/downloads/notebooks/UnderstandingTheFFT.ipynb) and the [blog entry](https://jakevdp.github.io/blog/2013/08/28/understanding-the-fft/)
+ Time domain & Frequency domain, http://multimechatronics.com/images/uploads/freshman%20tuts/Time%20Domain%20&%20Frequency%20Domain.pdf
+ What is the difference between Time domain and frequency domain?, http://www.researchgate.net/post/What_is_the_difference_between_Time_domain_and_frequency_domain10

### Fourier slice theorem
+ Filtered back projection: http://www.owlnet.rice.edu/~elec539/Projects97/cult/node2.html
+ http://en.wikipedia.org/wiki/Projection-slice_theorem
+ http://oftankonyv.reak.bme.hu/tiki-index.php?page=The+Central+Slice+Theorem
+ Back Projection, http://www.snaggledworks.com/em_for_dummies/back_projection.html
+ Image reconstruction, http://depts.washington.edu/nucmed/IRL/pet_intro/intro_src/section4.html
+ Back projection – 2D points to 3D : http://chenlab.ece.cornell.edu/people/adarsh/publications/BackProjection.pdf

### Error correction
+ http://en.wikipedia.org/wiki/Hamming_code
+ http://en.wikipedia.org/wiki/Hann_function

### DCT
+ http://en.wikipedia.org/wiki/Discrete_cosine_transform

----

# PHANTOM
+ http://en.wikipedia.org/wiki/Imaging_phantom
+ CT Images, https://www.nlm.nih.gov/research/visible/fresh_ct.html
   + https://mri.radiology.uiowa.edu/visible_human_datasets.html
+ https://sites.google.com/site/hispeedpackets/Home/shepplogan
+ [Reconstructing an Image from Parallel Projection Data](http://matlab.izmiran.ru/help/toolbox/images/transf13.html).
+ [Viewing the Radon Transform as an Image](http://matlab.izmiran.ru/help/toolbox/images/transf10.html).
+ http://bigwww.epfl.ch/thevenaz/shepplogan/
+ http://en.wikipedia.org/wiki/Computational_human_phantom
+ http://www.virtualphantoms.org/phantoms.htm

----

# FOSS

### FFTW
+ https://github.com/FFTW/fftw3
+ http://www.fftw.org/
+ https://en.wikipedia.org/wiki/FFTW
+ http://ab-initio.mit.edu/~stevenj/thesis-ch1.pdf

### TomoPy
+ https://github.com/tomopy/tomopy, [Docs](https://tomopy.readthedocs.org/)
+ Homepage: https://www1.aps.anl.gov/Science/Scientific-Software/TomoPy
+ Paper: http://scripts.iucr.org/cgi-bin/paper?S1600577514013939
   + PDF copy of [TomoPy: a framework for the analysis of synchrotron tomographic data](http://journals.iucr.org/s/issues/2014/05/00/pp5049/pp5049.pdf) Doga Gursoy, Francesco De Carlo, Xianghui Xiao and Chris Jacobsen.
      
----

# PUBLICATIONS

## Papers
+ [COMPARISON BETWEEN FREQUENCY DOMAIN AND TIME DOMAIN METHODS FOR PARAMETER RECONSTRUCTION ON NONUNIFORM DISPERSIVE TRANSMISSION LINES](http://www.jpier.org/PIER/pier43/01.0302031.L.Norgren.pdf), J. Lundstedt, M. Norgren.
+ The [tomographic reconstruction](http://en.wikipedia.org/wiki/Tomographic_reconstruction)
   + Paper: [Analytic and Iterative Reconstruction Algorithms in SPECT](Paper: jnm.snmjournals.org/content/43/10/1343.long) by Philippe P. Bruyant, PhD, 2002.
+ [2D and 3D ISAR image reconstruction through filtered back projection](http://www.researchgate.net/profile/Zhijun_Qiao/publication/258715731_2D_and_3D_ISAR_image_reconstruction_through_filtered_back_projection/links/00463537a7004e805c000000.pdf)
+ [Tomographic reconstruction of stress from photoelastic measurements using elastic regularization](http://www.researchgate.net/publication/30045506_Tomographic_reconstruction_of_stress_from_photoelastic_measurements_using_elastic_regularization).
+ [EIT Reconstruction Algorithms:  Pitfalls, Challenges and Recent Developments](http://arxiv.org/pdf/physics/0310151.pdf) by William R.B. Lionheart, 2004.

## Books
+ Kak A., http://www.slaney.org/pct/pct-toc.html

----

# Otsu Thresholding
+ http://www.labbookpages.co.uk/software/imgProc/otsuThreshold.html

----

# Julia Lib
+ Index : http://julia.readthedocs.org/en/latest/genindex/
+ http://julia.readthedocs.org/en/latest/stdlib/base/
+ http://stackoverflow.com/questions/25716547/type-i-discrete-cosine-transform-not-defined-found-in-julia-0-3-0

----

# DEPS
+ debugger, https://github.com/toivoh/Debug.jl
+ discrete cosine transforms, MDCT.jl


