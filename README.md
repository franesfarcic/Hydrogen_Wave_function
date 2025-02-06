# Hydrogen_Wave_function
This script defines the full hydrogen atom wavefunction in terms of its radial and angular parts and uses the Metropolis Monte Carlo algorithm to sample points from the probability density |psi(r,theta,phi)|^2. It then plots several orbital examples (1s, 2s, and 2p).

Utilizing cartesian-to-spherical conversion
I'm working on a function to convert Cartesian to spherical coordinates, enhancing visualization.
This will aid in analyzing the dispersion of the spatial location of orbitals.

Below is an annotated Python script that does the following:

Defines the full hydrogen-atom wavefunction in spherical coordinates.
This is split into:

A radial part 
𝑅
𝑛
ℓ
(
𝑟
)
R 
nℓ
​
 (r) that includes a normalization constant, an exponential decay, a polynomial factor 
(
2
𝑟
𝑛
𝑎
0
)
ℓ
( 
na 
0
​
 
2r
​
 ) 
ℓ
  (which “turns on” the angular momentum behavior near the origin), and an associated Laguerre polynomial
𝐿
𝑛
−
ℓ
−
1
2
ℓ
+
1
(
2
𝑟
𝑛
𝑎
0
)
L 
n−ℓ−1
2ℓ+1
​
 ( 
na 
0
​
 
2r
​
 )
that determines the number and location of radial nodes.

An angular part 
𝑌
ℓ
𝑚
(
𝜃
,
𝜙
)
Y 
ℓ
m
​
 (θ,ϕ) (the spherical harmonic) which describes the angular dependence (including the associated Legendre functions) and is responsible for the familiar “dumb-bell” or “donut” shapes when 
ℓ
≥
1
ℓ≥1.
Uses a Metropolis Monte Carlo algorithm to “sample” electron positions from the probability density

𝑃
(
𝑟
,
𝜃
,
𝜙
)
=
∣
𝜓
𝑛
ℓ
𝑚
(
𝑟
,
𝜃
,
𝜙
)
∣
2
P(r,θ,ϕ)=∣ψ 
nℓm
​
 (r,θ,ϕ)∣ 
2
 
where proposals are made by displacing the current 3D Cartesian point. (For orbitals that vanish at the origin, the code chooses a nonzero starting point.)

Plots a few examples (here we demonstrate the 1s, 2s, and 2p orbitals) as 3D scatter plots of the sampled positions.
