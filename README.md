# Netgen
[Netgen] is a tool for comparing netlists, a process known as LVS, which stands for "Layout vs. Schematic". This is an important step in the integrated circuit design flow, ensuring that the geometry that has been laid out matches the expected circuit.
Netgen is currently maintained by Tim Edwards (opencircuitdesign.com/netgen)

This repo contains pre-compiled binaries/libraries/etc of **Netgen Version 1.5** for **64-bit 18.04 Ubuntu Linux**. It's also tested on a light-weight Ubuntu-variant LXLE distro. If you are interested in compiling from the source, instructions in Section-[Compiling and Installing Netgen](#compiling-and-installing-netgen) should help.

## Setting up Netgen

- **NOTE**: The below is path is an example. Just make sure it matches your particular path.
```bash
export NETGEN_HOME=$HOME/eda-netgen
export PATH=$PATH:$NETGEN_HOME/bin
```

## Compiling and Installing Netgen

- This repo is compiled on Linux AWS Lightsail **5.4.0-1049-aws #51~18.04.1-Ubuntu**
- Clone and checkout the git repo:
```bash
git clone git://opencircuitdesign.com/netgen
cd netgen
git checkout netgen-1.5
```
- Some required packages if not already installed: **Tcl/Tk** (Ubuntu package names: ```tcl-dev, tk-dev```)
- Configure: To see all configure options ```./configure -----help```. To install in root with all default options just type ```./configure```
- To install it in a user directory: 
```bash
./configure --prefix=$HOME/eda-netgen
```
- Make and install:
```bash
make
make install
```
- **IMPORTANT** If this install directory needs to be used by other users by copying the install directory, replace the absolute paths: eg. ```/home/vlsi/tools/netgen-15 -> $NETGEN_HOME```
- In the following files:
```bash
bin/netgen, lib/netgen/tcl/netgen.tcl
```
- Additionally, since the ```netgen.tcl``` is sourced from ```bin/netgen``` the environment variable needs to be passed by adding the following statement to ```netgen.tcl```:
```tcl
set NETGEN_HOME $::env(NETGEN_HOME)
```

## Tasks
- [ ] Add examples


[OpenRAM]:              https://openram.soe.ucsc.edu/
[OpenRAMgit]:           https://github.com/VLSIDA/OpenRAM 
[OpenRAMpaper]:         https://ieeexplore.ieee.org/document/7827670/
[SCMOS]:                https://www.mosis.com/files/scmos/scmos.pdf
[NGSpice]:              http://ngspice.sourceforge.net
[NGSpiceMan]:           http://ngspice.sourceforge.net/docs/ngspice-html-manual/manual.xhtml
[Magic]:                http://opencircuitdesign.com/magic/
[Netgen]:               http://opencircuitdesign.com/netgen/


