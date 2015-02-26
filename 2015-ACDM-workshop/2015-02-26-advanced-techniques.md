+ [Claude Lecomte](#claude-lecomte)
+ [Wolfgang Scherer](#wolfgang-scherer)
+ [Christian Jelsch](#christian-jelsch)
+ [Dylan Jayatilaka](#dylan-jayatilaka)
+ [Simon Grabowsky](#simon-grabowsky)

----

# [Claude Lecomte](Title : “X , n polarized neutron joint refinement - Applications to organic radicals and molecular magnets.”)
* we model the ED and get the derived properties
* modeling the magnetic properties
* polarized neutron diffraction 

__refer to the talk slides__

----

# [Wolfgang Scherer](Title: “Chemical Bonding in Solid State Compounds”)

### reconstructing the ED from X-ray 
### experimental multio]polar refinements of a Diamond
* better the crystal,more the scattering features
* rietveld fitting is done with standard refinement.
* Always think of ligand fields in the charge density distribution

----
 
# [Christian Jelsch](MoPro workshop)
__PAUL__
christian.jelsch@univ-lorraine.fr
* load pw.hkl files
* For proteins R-free restraints are used for chemical imbalance and symmetry of the multiples
* Apply symmetriccal restraint to the atoms
* Compute the sigma and get the curve fitted.
* Crystallographic residual descriptors wR 2 F and wR 2 F free as a function of multipole symmetry restraint sigma (σ sym ) for the first R-free series of tests.

### 10.5 - HOW TO compute average free R-factors
LOOP lp1 20
FREE HKL 20 LOOP# lp1

SHAK UIJ 0.003
SHAK XYZ 0.003
REFI ALL 9 DAMP 0.7 BLOD NOHO   ! in the fortran code, add the parameter `NOHO` for no high-order refinement and `BLOD will take less time
WRIT RFAC #
ADDR lp1

WRIT FREE 

----

# [Dylan Jayatilaka](Title : “X-ray wavefunction refinement - Introduction")

* wavefunction (Ψ) is the best model: for single state functions

* change the orbitals to fit the WF - 8Ang of charge and then iterate 
* the blue ones are refinable parameters
* e ik ·t = phasse factor that can be changed

* slide#23:  χ 2 is as small so reserve 10-15% of the data for the fit. 

__refer to the talk slides__

----

# [Simon Grabowsky](Title: "X-ray wavefunction refinement - Application")

mean abs deviation

blue = mean diff 
red and green = Standard differentiation
pale gray = independent atom modeling
__refer to the talk slides__


