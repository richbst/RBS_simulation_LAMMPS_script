Example LAMMPS scripts for growing, thermocycling, and cooling polydisperse films.
The first requires a LAMMPS compilation containing the modifications stored in the repository RBS_simulation_LAMMPS_code.

in.growh120-11
> deposition of size-dispersed Lennard-Jones atoms (12 sizes) onto a rigid substrate of slightly smaller atoms into a box 10x10x40, the sides having periodic boundary conditions
> requires mods to the standard LAMMPS to allow random selection of 12 different sizes for deposition or swapping
> notes on operation at the head of the script.

in.heatxsspoly
> Uses as input atom dump file produced by the grow-script
> script parameters must be set to match film growth temp and file label
> Heats from a standard start temp to above the relaxation temperature and back twice
> creates an atom dump and a tempdens file that are used with python codes (see RBS_simulation_python) to determine mobility and density in separate analyses.

in.cool-pe-dens
>cools film created by the grow-script to approximately zero temp using a baristas on the side walls to maintain zero lateral pressure. 
>outputs average potential energy and film density at each temperature
>and atom dump file for calculation of inherent structures using pascal routines in RBS_simulation_python or an Ovito function.

in.anneal_lng2_film
>Used in measurement of film relaxation time. This script heats film very rapidly to an annealing temperature, then creates up to 74 atomdump files at 15% intervals.
>They are used by intermedscatt-anneal-xy_long.py to calculate the self-intermediate scattering function for the film. Provision is made to delay the start of
>atom dumps until the film is equilibrated at the new temperature.
