# Hydrogen_Wave_function
This script defines the full hydrogen atom wavefunction in terms of its radial and angular parts and uses the Metropolis Monte Carlo algorithm to sample points from the probability density |psi(r,theta,phi)|^2. It then plots several orbital examples (1s, 2s, and 2p).

# Utilizing Cartesian-to-Spherical Conversion

I'm working on a function to convert Cartesian to spherical coordinates, enhancing visualization.  
This will aid in analyzing the dispersion of the spatial location of orbitals.

Below is an annotated Python script that does the following:

## 1. Defines the Full Hydrogen-Atom Wavefunction in Spherical Coordinates

This is split into:

- A **radial part** $R_{n\ell}(r)$ that includes a normalization constant, an exponential decay,  
  a polynomial factor $\left(\frac{2r}{na_0}\right)^\ell$ (which “turns on” the angular momentum behavior near the origin),  
  and an associated Laguerre polynomial:

  $$L_{n-\ell-1}^{2\ell+1} \left( \frac{2r}{na_0} \right)$$

  that determines the number and location of radial nodes.

- An **angular part** $Y_{\ell}^{m}(\theta, \phi)$ (the spherical harmonic) which describes  
  the angular dependence (including the associated Legendre functions)  
  and is responsible for the familiar “dumb-bell” or “donut” shapes when $\ell \geq 1$.

## 2. Uses a Metropolis Monte Carlo Algorithm

The script "samples" electron positions from the probability density:

$$P(r, \theta, \phi) = |\psi_{n\ell m}(r, \theta, \phi)|^2$$

where proposals are made by displacing the current 3D Cartesian point.  
(For orbitals that vanish at the origin, the code chooses a nonzero starting point.)

## 3. Plots a Few Examples

Here we demonstrate the **1s, 2s, and 2p orbitals** as 3D scatter plots of the sampled positions.

---

Below is the complete code. You can save it as (for example) **`hydrogen_metro.py`**  
and run it (provided you have NumPy, SciPy, and Matplotlib installed).

​
 (r,θ,ϕ)∣ 
2
 
where proposals are made by displacing the current 3D Cartesian point. (For orbitals that vanish at the origin, the code chooses a nonzero starting point.)

Plots a few examples (here we demonstrate the 1s, 2s, and 2p orbitals) as 3D scatter plots of the sampled positions.
