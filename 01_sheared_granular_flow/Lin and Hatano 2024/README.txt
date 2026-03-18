README file for GB ellipsoid simulation script associated with
"Rheology and Structure of Smectite Clay: Insights from Molecular Dynamics"
by Z.-Y. Lin and T. Hatano (submitted)

"LAMMPS_script" directory include the input script to use in LAMMPS.
The script for compression, shear, and rest are in files 
"in.1_compression", "in.2_shear001_press1000", and
"in.3_rest_shear1_press1000", respectively.
The instructions for installing and running 
simulations on LAMMPS is given below.

========================================
LAMMPS_script
========================================
Input script used in LAMMPS simulations
for (1) compression, (2) shear and, (3) rest.

The version of LAMMPS used for running the simulation is "23Jun2022"
and it can be downloaded from the LAMMPS older version repository at
https://download.lammps.org/tars/index.html .

After decompress the .tar file, add additional package
of LAMMPS: ASPHERE and OPENMP
and build the code with command:

cd lammps-23Jun2022/src/
make yes-asphere
make yes-openmp
make omp

Successful building creates a new executable "lmp_omp".
Run a LAMMPS simulation script (e.g. compression)
with the following command:

export OMP_NUM_THREAD= [M]
mpirun -np [N] ./lmp_omp -sf omp -in in.1_mix4000_compression

This command runs the simulation script "in.1_mix4000_compression"
on [M]*[N] cores, with [N] MPI tasks and [M] OpenMP threads.

****************************************

Use of any or all the data included in this deposit
must cite the associated publication:
"Rheology and Structure of Smectite Clay: Insights from Molecular Dynamics"
by Z.-Y. Lin and T. Hatano (submitted), and include the DOI link associated
with this data in the Zenodo digital repository.
