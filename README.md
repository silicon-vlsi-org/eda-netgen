# Netgen
### Current distribution version 1.5.185
Precompiled for **64b 18.04 Ubuntu and Ubuntu-based Linux**. It's also tested on a light-weight Ubuntu-variant LXLE distro. If you are interested in compiling from the source, instructions in [ADMIN.md:Compiling and Installing Magic](ADMIN.md) should help.

[Netgen] is a tool for comparing netlists, a process known as LVS, which stands for "Layout vs. Schematic". This is an important step in the integrated circuit design flow, ensuring that the geometry that has been laid out matches the expected circuit.
Netgen is currently maintained by Tim Edwards (opencircuitdesign.com/netgen)

## Table of Content
- [Downloading & Setting Up Netgen](#downloading-&-setting-up-netgen)
- [Quick Start Guide](#quick-start-guide)

## Downloading & Setting Up Netgen

- Change directory ```cd``` to install directory <INSTALL_DIR> e.g. ```/home/user/cad```
- To download from the ```git``` repository:
  - ```git clone https://github.com/silicon-vlsi-org/eda-netgen```
- Change directory to the installed `netgen` directory eg. ```cd eda-netgen```
- Checkout the desired version: ```git checkout v1.5.185```
  - To make sure you are on the right version type ```git branch``` and your output should have a line like this :
  - ```* (HEAD detached at v1.5.185)```

- Add the following environment variables in your `~/.bashrc` (**NOTE**: The path below is an example, make sure it matches your particular path) 

```bash
export NETGEN_HOME=$HOME/eda-netgen
export PATH=$PATH:$NETGEN_HOME/bin
```

## Quick Start Guide
FIXME: Add examples to the repo

