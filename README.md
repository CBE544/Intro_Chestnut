# Introduction to Chestnut

## First time log in  ##
Add the following line to your ~/.bashrc to initialzie enviromet and modules for Vojvodic group.   

`source  /scratch/alevoj1/Scripts/group_bashrc`

You should see a new section `/opt/user/p_alevoj/modulefiles/` added when you type `module avail` from terminal
```bash

[liangzha@chestnut-login lib]$ module avail

-------------------------------------------------------------- /opt/user/p_alevoj/modulefiles/ ---------------------------------------------------------------
ase/3.13.0               ase-vasp/dev             ase-vasp/run             gcc/vasp-vtst-beef/5.4.1 vtk/7.1.1
ase/3.9.1                ase-vasp/prepare-only    gcc/qe-pybeef/5.1        vojgrp-env

--------------------------------------------------------------- /usr/share/Modules/modulefiles ---------------------------------------------------------------
dot         module-git  module-info modules     null        use.own

------------------------------------------------------------------- /opt/seas/modulefiles --------------------------------------------------------------------
chestnut                      gcc/qe/default                gpu/gcc/lammps/31Mar17        intel/intelpython2/default    intel/vasp/default
gcc/fftw/double/3.3.6         gcc/vasp/5.4.1                gpu/gcc/lammps/default        intel/intelpython3/2017.2.045 mygroup
gcc/fftw/single/3.3.6         gcc/vasp/default              gpu/gcc/openmpi/2.1.0         intel/intelpython3/default    mynull
gcc/lammps/default            global                        gpu/gcc/openmpi/default       intel/lammps/default          template
gcc/lammps/misc/31Mar17       gpu/cuda/8.0                  intel/17                      intel/lammps/misc/31Mar17
gcc/openmpi/2.1.0             gpu/cuda/default              intel/17.0.3                  intel/openmpi/2.1.0
gcc/openmpi/default           gpu/gcc/gromacs/5.1.4         intel/icc                     intel/openmpi/default
gcc/qe/6.1                    gpu/gcc/gromacs/default       intel/intelpython2/2017.2.045 intel/vasp/5.4.1
```

## Package available ##
