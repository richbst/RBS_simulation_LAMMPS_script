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
> creates an atom dump and a tempdens file that are used with python codes (see RBS_simulation_python) to determine mobility and density in separate analyses
> also modified to heat very rapidly from deposition temp and hold at anneal temp while writing atomn dumps at ~15% intervals

in.cool-pe-dens
>cools film created by the grow-script to approximately zero temp using a baristas on the side walls to maintain zero lateral pressure. 
>outputs average potential energy and film density at each temperature
>and atom dump file for calculation of inherent structures using pascal routines in RBS_simulation_python or an Ovito function.
