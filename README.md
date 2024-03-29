# Initial considerations

**Fundamental questions**:

- In equilibrium with gas phase O$`_2`$, Which of Pt, PtO, and PtO$`_2`$ is the most stable?
- How should we normalize the energy of the different materials?
- We need a method that includes information about the temperature and pressure of O$`_2`$. 

**Basic principles**

*Phase:* it is a homogeneous region of matter in which there is no spatial variation in average density, energy, composition, or other macroscopic properties.

At constant T and P in a single-component system, the phase that is observed is the one which has the lowest Gibbs free energy per particle, or, equivalently, the lowest chemical potential μ(T, P).

# General Theory
Grand potential of a metal oxide can be expressed as 

$$ \Omega (T,\mu_O, \mu_M) = E(N_M, N_O) - TS - \mu_O N_O - \mu_M N_M$$

Where $`E(N_M, N_O)`$ is the internal energy of the metal oxide, S is the material's entropy, and $`\mu_a`$ is the chemical potential of atomic species $`a`$. We can use this expression to define the grand potential of each material $`\Omega_i`$. We can associate the $`E(N_M, N_O)`$ with the total energy from a DFT calculation. 

The chemical potential of oxygen is defined by 

$$  \mu_{O_2} = \mu_{O_2}^o (T, p^o) + kT \ ln(p_{O_2}/p_{O_2}^o) $$

Where $`p_{O_2}^o`$ is the pressure of oxygen at 1 bar. Other useful relation is 

$$  \mu_{O_2} = E_{O_2}^{total} + \tilde \mu_{O_2}^o (T, p^o) + kT \ ln(p_{O_2}/p_{O_2}^o) $$

Here, $E_{O_2}^{total}$ is the total energy of an isolated oxygen molecule at $`T = 0`$ K. The second term on the rigth is the difference in the chemical potential of O$`_2`$ between $`T = 0 `$ K and the temperature of interest at the reference pressure. This chemical potential difference can be evaluated in the JANAF Thermochemical Tables. 

The chemical potential of molecular oxygen and atomic oxygen are related by 

$$  \mu_O = \dfrac{1}{2} \mu_{O_2}  $$


# Theory for metal clusters
The grand potential ($` \Omega `$) divided by N and assuming a constant number of metal atoms (e.g. Pt$`_2 `$)

$$  \omega (T,\mu_O, n) = \Delta E_{F,corr} (T) - T \cdot S_{Pt_2(O_2)n} + T \cdot S_{Pt_2}  - n \cdot \tilde \mu_{O_2} (p, T)  $$

Where $n$ is the number of oxygen molcules. A (p,T)-phase diagram can be constructed using the potential $` \omega `$. We can know the number $n$ of O$`_2`$ molecules which minimizes $` \omega `$
for a specified temperature and oxygen pressure. 

The formation energy of Pt$`_2`$(O$`_2`$)$`_n`$ clusters ($` \Delta E_{F,corr} (T) `$) is calculated as 

$$  \Delta E_{F,corr} = E_{Pt_2 (O_2)n} - E_{Pt_2} - n\cdot  E_{O_2} + E_{corr} (T) $$

E$`_{corr}`$ is introduced to account of the zero-point energy. The (T,p) dependence part of the chemical potential is expressed as 

$$  \tilde \mu_{O_2} (p,T) = \Delta H_{O_2} (p_0, T) - T\cdot S_{O_2} (p_0, T) + RT \ ln(p/p_0) $$

Where $` \Delta H_{O_2} `$  and $` S_{O_2} `$ are taken from the NIST database. Addionally, note that 

$$  \mu_{O_2}  = E_{O_2} + \tilde \mu_{O_2}   $$

# Thermochemistry

### Zero-point vibrational energy

$$ E_0 = U_0 = E_{elec} + \sum_{i}^{modes} \dfrac{1}{2} h \omega_i  $$

Where $` E_{elec}`$ is the energy of the stationary point on the PES. 

### Canonical ensemble

The partition function for the canonical ensemble is written as 

$$
Q(N,V,T) = \sum_i e^{E_i(N,V)/kT}
$$

Where i runs over all possible energy states of the system. The thermodynamic potentials are defined by the expressions

$$
U = kT^2 \bigg ( \dfrac{\partial ln \ Q}{\partial T} \bigg )_{N,V}
$$

$$
H = U + PV
$$

$$
S = k ln \ Q + kT \bigg ( \dfrac{\partial ln \ Q}{\partial T} \bigg )_{N,V}
$$

$$
G = H - TS
$$

### Gas phase approximation

We assume that our ensemble is an ideal gas. This implies that gas molecules do not interact with each other. 

$$
Q(N,V,T) = \dfrac{[q(V,T)]^N}{N!}
$$

Where the factor $`1/N! `$ derives from the quantum mechanical indistinguishability of the particles. Now we assume
that the molecular energy $` \varepsilon `$ can be expressed as a separable sum of electronic, translational, rotational, 
and vibrational terms. 

$$
q(V,T) = q_{elec}(T)q_{trans}(V,T)q_{rot}(T)q_{vib}(T)
$$

### Molecular electronic partition function

The electronic contribution of entropy and internal energy is 

$$
U_{elec} = 0 \qquad \qquad S_{elec} = R \ ln(2S + 1)
$$

### Molecular translational partition function

The usual standard state is 1 atm pressure (corresponding to a standard-state molar volume of 24.5 L at 298 K). 
The thermodynamic potential for the translational contribution gives 

$$
U_{trans} = \dfrac{3}{2} RT \qquad \qquad S_{trans}^{o} = R  ln \bigg [ \bigg ( \dfrac{2\pi M k T}{h^2} \bigg )^{3/2} \dfrac{kT}{P^o} \bigg ] + \dfrac{5}{2}  R
$$

The superscript "o" indicates that a "standard state" is being referred. This contribution is independent of the molecular structure. 
$`  S_{trans}^{o} `$ can be computed trivially as soon as the molecular weigth is specified. The translational partition function is a function of both temperature and volume.


### Molecular Rotational Partition Function

For linear molecules

$$
q_{rot}^{linear} (T) = \dfrac{8\pi^2 I k T}{\sigma  h^2} 
$$

Donde $` \sigma `$ is 1 for asymmetric linear molecules and 2 for symmetric linear molecules. The thermodynamic potentials using the partition function gives 

$$
U_{rot}^{linear} = RT \qquad \qquad S_{rot}^{linear} = R \bigg [  ln \bigg (  \dfrac{8\pi^2 I k T}{\sigma h^2} \bigg ) + 1 \bigg ]
$$

For non-linear molecules gives

$$
q_{rot} (T) = \dfrac{\sqrt{\pi I_A I_B I_C}}{\sigma} \bigg ( \dfrac{8\pi^2 k T}{h^2} \bigg )^{3/2} \qquad \qquad
U_{rot} = \dfrac{3}{2} RT   \qquad \qquad
S_{rot} = R \bigg [  ln \bigg (   \dfrac{\sqrt{\pi I_A I_B I_C}}{\sigma} \bigg ( \dfrac{8\pi^2 k T}{h^2} \bigg )^{3/2} \bigg ] + \dfrac{3}{2} R
$$

### Molecular Vibrational Partition Function

The full partition function for a non-linear molecule is 

$$
q_{vib}(T) = \prod_{i=1}^{3N-6} \bigg ( \dfrac{1}{1-e^{-h\omega_i/kT}}  \bigg ) 
$$

Upper limit would be 3N -5 for linear molecules. The thermodynamic potentials are

$$
U_{vib} = R \sum_{i=1}^{3N-6} \dfrac{h\omega_i}{k(e^{h\omega_i/kT}-1)}   
$$

$$
S_{vib} = R \sum_{i=1}^{3N-6} \bigg [ \dfrac{h\omega_i}{kT(e^{h\omega_i/kT}-1)} -ln(1-e^{-h\omega_i/kT}) \bigg ]
$$


## References
* David S. Sholl, Janice A. Steckel. (2009). *Density Functional Theory: A Practical Introduction*. DOI:10.1002/9780470447710

* Cristopher J. Cramer. (2004). Essentials of Computational Chemistry: Theories and models. Second edition. Wiley

* Karsten Reuter and Matthias Scheffler. *Physical Review B*. 2001, 65, 035406. DOI: 10.1103/PhysRevB.65.035406

* Mina Taleblou, Matteo Farnesi Camellone, Stefano Fabris, and Simone Piccinin. *The Journal of Physical Chemistry C*. 2022, 126, 10880−10888. DOI: 10.1021/acs.jpcc.2c02176

* David Buceta et al. *Chemistry -- A European Journal*. 2023, 29, e202301517. DOI: 10.1002/chem.202301517  
