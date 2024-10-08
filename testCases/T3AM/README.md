# Flat plate transitional boundary layer - T3A- case

Flat-plate transitional 2D boundary layers flows without pressure gradient.

The flat plate $3 m$ long starts at $x=0.04 m$. The leading edge is circular arc with readius $7.5 mm$. The domain extends up to $1 m$ from the flat plate.

## Boundary conditions
The boundary conditions were set up according to Menters, Smirnov et al.

- Inlet velocity $U = 19.8$ $ms^{-1}$
- Turbulence intensity at the inlet (i.e. $0.04 m$ before the plate) $I = 0.9\\%$
- Turbulent/laminar viscosity ratio at the inlet $\nu_t/\nu = 8$.

## Simulation
The mesh density can be selected by using a command line argument to `Allrun`,
so
- `./Allrun coarse` or `./Allrun` runs the simulation using a mesh with $26 820$
  cells, average $y^+ = 1.30$
- `./Allrun medium` or `./Allrun` runs the simulation using a mesh with $107 280$
  cells, average $y^+ = 0.65$
- `./Allrun fine` or `./Allrun` runs the simulation using a mesh with $429 120$
  cells, average $y^+ = 0.34$

## Expected results

![Friction coefficient at the wall](./validation/figures/Rex_vs_cf.png)

![Turbulence intensity along the plate](./validation/figures/x_vs_u.png)

## References:
- [ERCOFTAC T3A- 0.9% test-case](http://cfd.mace.manchester.ac.uk/ercoftac/doku.php?id=cases:case020)
- SAVILL, A. M. Some recent progress in the turbulence modelling of by-pass transition. *Near-wall turbulent flows*, 1993, 829-848.
- SAVILL, A. M., 1996. One-Point Closures Applied to Transition. *In: HALLBÄCK, M., HENNINGSON, D.S., JOHANSSON, A.V., ALFREDSSON, P.H. (ed.), Turbulence and Transition Modelling*. Springer, Dordrecht. p. 233–268, doi:10.1007/978-94-015-8666-5_6.
- MENTER, Florian R., SMIRNOV, Pavel E., LIU, Tao and AVANCHA, Ravikanth, 2015. A one-equation local correlation-based transition model. *Flow, Turbulence and Combustion*. 5 December 2015. Vol. 95, no. 4, p. 583–619. doi:10.1007/s10494-015-9622-4. 
