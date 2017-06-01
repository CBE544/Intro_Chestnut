# Introduction to Chestnut
## X-forwarding software you need before login 
### Mac OSX
Download and install:

* [XQuartz](http://www.xquartz.org/)

To prevent X11 from timing out, open the terminal and type:

### Windows

Download and install:

* [PuTTY](http://www.putty.org/)
* [Xming](http://sourceforge.net/projects/xming/) (Note: disable automatic installation of PuTTY with Xming. The above installer is a newer version)

### Linux (Debian-based, e.g. Ubuntu)
From the terminal

## Logging onto the Clusters

login with your Pennkey username and password username.
Follow the instructions below for your system:

### Mac OSX

Open "Applications-> Utilities -> Terminal" or "Command+Space" to search Terminal using "spotlight search"
In a terminal:
```bash
ssh -X Pennkey@chestnut-login.seas.upenn.edu
```

### Windows 
Launch Xming. You will always need to have this open in order to forward graphical windows from the external clusters.

Start PuTTY, and:

* “Session” → “Host Name” `username@hestnut-login.seas.upenn.edu` for **Chestnut**
* “Connection” → “SSH” → “X11” check “Enable X11 forwarding”
* Back in “Session”, you can **save these settings for next time**.

You can start putty several times, if you need several terminal windows; only one instance of Xming needed.


### Linux ###

In a terminal:
```bash
ssh -X Pennkey@chestnut-login.seas.upenn.edu
```

## First time log in  ##
Add the following line to your `~/.bashrc` to initialzie enviromet and modules for Vojvodic group.   

`source  /scratch/alevoj1/Scripts/group_bashrc`

```bash
source ~/.bashrc
```

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

run Python in interactive mode by typing:

```bash
python
```

and make sure the following commands work:

```python
import ase
import numpy
```

## vojgrp-env ##
```tcl
#%Module1.0#####################################################################
##
## mygroup: install my group specific package directory
##

module load ase/3.9.1
# Export to User.

set base "/opt/user"
set primary_group [exec id -ng]
switch -glob $primary_group {
  p_* {
    prepend-path    PATH            $base/$primary_group/bin
    prepend-path    PATH            $base/$primary_group/bin/vtstscripts
    prepend-path    PYTHONPATH      $base/$primary_group/lib/python2.7/site-packages
    prepend-path    PYTHONPATH      $base/$primary_group/lib64/python2.7/site-packages
    prepend-path    MANPATH         $base/$primary_group/share/man
    prepend-path    LD_LIBRARY_PATH $base/$primary_group/lib
    prepend-path    LIBRARY_PATH    $base/$primary_group/lib
    prepend-path    C_INCLUDE_PATH  $base/$primary_group/include
    prepend-path    ESP_PSP_PATH    /scratch/alevoj1/esp-psp/v2/
    prepend-path    VASP_PP_PATH   /scratch/alevoj1/vasp_psp/pseudo52/
  }
}
```

## Package available ##
```bash
VASP-vtst-beef
QuantumEspresso(QE)-Pybeef
ASE and interfacer to VASP/QE
gnuplot
povray
vaspkit
Python package: matplotlib, numpy, scipy (system-wide), sklearn (group)
```

