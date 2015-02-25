* [Philip-Coppens](#philip-coppens)
* [Piero Macchi](#piero-macchi)
* [Jacob Overgaard](#jacob-overgaard)
* [Christian Jelsch](#christian-jelsch)

----

# Philip Coppens (Title: “A Birds Eye Introduction to X-ray Charge Density Analysis and Some Recent Developments”)

### Basic principals of X-Ray charge dnsities analysis and an intro to excitation densities

* Atoms in a mol or crystal are not spherical.
* The experimental xray charge density minus the charge density of spherical atoms centred at the neutron positions with neutron parameters.
* set of nuclear co-ord and detailed map of electron distribution.

### Multipoles definition if pseudoatoms
* pseudoatom is not so much an atom but something that takes the bonding density of molecules.

#### Definitions
* Multipoles are a complete set of angular functions and the higher you go the more object sets you can represent.
* Niels Hansens theory - Charge density refinement program MOLLY, precursor of XD program
* Density functions looks like orbitals.
* Modifications of pseudoatoms cannot be rigid because of electron-electron repulsion. Atoms that are positive then the same charge density will occur for the same charge density.

### X-Ray charge density multipole model
* Static Electron Density (ED) is the super position of aspherical pseudoatoms.
* Formalism for high order data can show core expansion and contraction of coredeformations

### Diff between cd-mulltipoles and atomic orbitals
* Spherical Harmonic basis functions. 
* Normalization of spherical harmonic orbital funcion needs different normalization of density technique.

### Electron density in terms of obitals
* ONE-electron  density - diagonal, atom-centered terms and cross terms, including 2 center terms. 
* Density functions are products of orbital functions : Y10.Y01 = Y21

### Electron Density in terms of orbitals 
* Mathematical corelation between multipole populations and orbital populations if 2 center terms are neglected.

### Total density 

### Results
* Deformation density from multipole refinement : 1. dynamic and static function plots of *Static* total density. 

CONCEPTS: 
+ Bond paths
+ Bond critical paths
+ atomic basinsan
* Laplacian : charge concentrations - if the peak is big second order derivative is big
* An atomic charge is not an atomic charge


### Analysis of the toplogy of charge density - quantum theory

### Charge density and structural dynamics
* Define excitation densities :  a laser pump xray probe technique with the BioCARS hutch at APS Argonne.
* Definition of Activation difference map: Charge density is hard to discern but the method to calculate the ES (excited state) geometry on GS (ground state) 
 Structure and subtract grids.
* Coinage metal compound Ag2Cu2L1

### Ag Cu calculation of frontier molecular orbitals - luminous compounds

----

# Piero Macchi
## Piero Macchi “General Aspects of Multipole Modelling”

### Multipolar Expansion 
* ED is expanded in multi polar centered atomic functions 
```
P is the unknown value
rho is the fitting model
```
* There are two kind of functions - radial part and angular part

### Choice of radial function  

GAussian or Slater functions are used fir ht angular behaviour of Rho to he finite in origin/.

### Core orbitals 
* are a combination of slate functions and when you take a square of the function you get the 
* spherical valence calculation 


### Which wave function for core and valence
* Roothan-Hartree-Fock calculation on ground state isolated atoms and more relevant ions. Each atonic orbital is expanded in a series of Slater functions 


### Relativistic atomic wave funtions 

* Zero order RElativisti approximation  DFT calculation on isolated atoms 
* Scattering factor efrrors with respect to te dirac equation

### Deformation valence density (DEFV)
* a single slater function will be used for the seta exponet constructed from the single valence orbitals
* Satisfy a poisson equation for radial equation the N has to be larger
* Valence and core fraction are the largest near the core - to refine the core, then resolution is higher but not from the valence

### D orbitals of transition metals - ex 3d orbitals of Fe
* Full orbital expansion in the slater function

### 3d/4s orbital of transition metals
* CLose in energy abd far in space

### Angular functions and spherical harmonics

Orbitals vs. multipoles
* linesr combination of sperical harmonics 
the xpansion goes maximum for product of two L + L' (l prime) = that mean an approdimation of linear combination of atoms centered - add the odd and even electronic density

### Fitting the density of H2
* fitting with monopolar functions - but will have spherical atoms with overlap density. 
* Expand diagonal dipoles but it will not answer
* We need dipoles and quadripolar functions to fit the density of two Hydrogen atoms

### d-orbitals and metal atoms
* make and assumption that the d-orbital and othe atom does not overlap and it allows to get the refinement
* Hexadecapole refinement - no overlap among carbon atoms
* dipoles and octopoles are very small and only describe 3d product.
* TRy refining 3s occupation

### Multipolar expansions in the Periodic table - summary
* H cannot be described a s monpole
* alkaline and noble gases can be described by spherical functions
* Hexa/Deca to octapole level or more for lower elements 
* Mirror Symmetry will force you to reduce the 3m symmetry implying a distorted hybridization models.


----

# Jacob Overgaard (Title : “Importance of Modelling H-Atoms”)

### H-atoms

+ Hydrogen and xrays - in standard xray crystal structure determination, thermal mption is deconvoluted from electronic effects by application of hte Born-Oppenheimer approximation
+ atomic pdf can be isotropic or anisotropic - H does not have core electrons. 

### Hydrogen bonding (HB)
* H atom is bonded to a more electronegative atom, the donor atom
* the positive hydrogen is attracted to negative H partners
   a. normal and weak HB with double well bonding
   b.
   c.
* Resonance is non-H structure - with neg. or pos. charge.
```
1. Use neutron data to obtain unbiased position and adps
2. obtain anisitropic Hatom adp by TLS analysus if the non Hskeleton and internal vibrational amplitude
3. Hirshfeld 
```

### How to combine X and N (neutron) data
* Grow the crystal - the bigger, the better but this is really hard to do.

### Scaling - UIJXN program
* systematic 

### HB Characterization
* module XDPROP can be used to calculate the laplacian distrributuobn - used to studey the nature of the chemical bonding in the hydrogen bond.
* Density and laplacian along the O...H bond is interesting 
 
### Bond energies
* empirically corelate the toological propertios of the HB bcp.


----
 
# Christian Jelsch  (MoPro)

ATOMS      30

ATOM     1  NT    ala    1  0.427410  0.050010  0.613830  1.000  1  N
 ZX    CA    H2    OCT    K1      V0    M0    Q0
UANI   0.012840  0.010190  0.009590  -.000240  0.005260  -.000530

five valence electrons

  5.     0.     0.     0.     0.     0.     0.     0.     0.     0.
  0.     0.     0.     0.     0.     0.     0.

then the list of atoms til the end 


FILT 1.0 (should not be refined - it is fixed)



! <refinement> scale 
SELE  SCA
REFI LS 4  (4 refinement cycles)
WRIT RFAC  ( write r factorial) 

WRIT FOUR 


For proteins use a distance restraint 
for small molecules use a constraint

CONDIS N1 H1 1 1.08
DISTANCE N1 H1 1 1.08  0.01 (<--standard deviation)

after changing values run the program again


GET protein structure file with hydrogen atoms, except water molecules

### Mol

xyz 555   01
    Tr =0  sign =
    
    655 01   x+1
    455 01  x-1 
    467 01 x-1 y+1 z+2
    
    
xyz 655 02
   sym#2 + a'    
   
   555 51  -x -y -z
   
