# Introduction to Chestnut
## Log in to Chestnut ##
# Getting Started
1. [Logging Into the Computing Clusters](../Clusters/)
2. [Basic UNIX](../UNIX/)
3. [Python](../Python/)

____

## Logging Into the Computing Clusters

Once you account on Stampede has been activated. Follow the instructions and tests to make sure everything is set up properly and functional.

## Contents
1. [Installation](#installation)1`
2. [Logging On](#logging)
3. [First Time Logging On](#first-time)
4. [Making Sure Everything Works](#testing)

<a name='installation'></a>

## Installation

### Mac OSX
Download and install:

* [XQuartz](http://www.xquartz.org/)

To prevent X11 from timing out, open the terminal and type:

```bash
mkdir -p ~/.ssh
echo $'\nHost *\n ForwardX11Timeout 1000000\n' >>~/.ssh/config
```


### Windows

Download and install:

* [PuTTY](http://www.putty.org/)
* [Xming](http://sourceforge.net/projects/xming/) (Note: disable automatic installation of PuTTY with Xming. The above installer is a newer version)


### Linux (Debian-based, e.g. Ubuntu)
From the terminal
____

<a name='logging'></a>

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

* “Session” → “Host Name” `username@stampede.tacc.utexas.edu` for **Stampede**
* “Connection” → “SSH” → “X11” check “Enable X11 forwarding”
* Back in “Session”, you can **save these settings for next time**.

You can start putty several times, if you need several terminal windows; only one instance of Xming needed.


### Linux ###

In a terminal:
```bash
ssh -X Pennkey@chestnut-login.seas.upenn.edu
```
____

<a name='first-time'></a>

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
