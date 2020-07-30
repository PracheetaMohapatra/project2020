# Table of Contents 
- [Overview](#Overview)
    - [Cloning the Repo](#Cloning-the-Repository)
    - [Suggested Directory Structure](#Suggested-Directory-Structure)
- [NGSpice](#NGSpice)
- [OpenRAM](#OpenRAM)
- [Tasks](#Tasks)

# Overview

This is the repository for the VLSI Project 2020. This repo contains the eda tools, Labs, assignments, docs, etc. related to the project.

## Cloning the Repository
```bash
git clone https://www.github.com/silicon-vlsi/project2020
```
## Suggested Directory Structure
```bash
<HOME_DIR> [eg. /home/vlsi]
   ├── project2020	[Git repo, DO NOT  work in this Dir]
   ├── Desktop
   |    ├── myLab	[Your work dir	]
   ├─ OpenRAM		[Git repo for OpenRAM, DO NOT work in this dir]
   ├─ OpenSTA		[Git repo for OpenSTA, DO NOT work in this dir]
```

# NGSpice
[NGSpice] is a open source spice simulator for electric and electronic circuits. After cloning this repo, a precompiled version (compiled in 64-bit LXLE/Ubuntu) will be available in `<PATH-TO-REPO>/project2020/eda/ngspice-32`. Add the following environment variables in your `~/.bashrc`
```bash
export  SPICE_LIB_DIR=$HOME/projects/project2020/eda/ngspice-32/glnxa64/share/ngspice
export  SPICE_EXEC_DIR=$HOME/projects/project2020/eda/ngspice-32/glnxa64/bin
export  PATH=$PATH:$SPICE_EXEC_DIR
```
There is a initialization script in `$SPICE_LIB_DIR/scripts/spinit`. You can overwrite any of the initilization by adding commands to a local `~/.spiceinit` .

## Getting Started
You can open a text editor create a *netlist* of the intended circuit for example of a voltage divider as shown below (say filename `divider.sp`):
```spice
First line in ngspice is always the title line
* This is a comment line
Vbat    vin     0       DC 5
R1      vin     vout    1k
R2      vout    0       1k

.control
tran 0.1u 1u
.endc

.end
```

# OpenRAM
[OpenRAM] is an award winning open-source Python framework to create the layout, netlists, timing and power models, placement and routing models, and other views necessary to use SRAMs in ASIC design.

- Find the project on [GitHub][OpenRAMgit] with documentation to get started
- Read the [ICCAD Paper][openRAMpaper]
- For this project we will use the [SCMOS] technology, a scalable 0.5u CMOS technology.

# Tasks
- [x] Install LXLE on Virtual Box
- [x] Compile ngspice-32 on LXLE and add to the repo.
- [x] Add the [SCMOS] spice models to the ngspice directory.
- [ ] Add a NGSpice section with a quickstart guide to this README
- [ ] Create a customized `Sue` schematic editor and add to repo.
- [ ] Compile [Magic] in LXLE and add to the repo.

* * *

[OpenRAM]:              https://openram.soe.ucsc.edu/
[OpenRAMgit]:           https://github.com/VLSIDA/OpenRAM 
[OpenRAMpaper]:         https://ieeexplore.ieee.org/document/7827670/
[SCMOS]:                https://www.mosis.com/files/scmos/scmos.pdf
[NGSpice]:              http://ngspice.sourceforge.net
[Magic]:                http://opencircuitdesign.com/magic/
