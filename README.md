# Netgen
### Current distribution version 1.5.272
Precompiled for **64b 22.04 Ubuntu and Ubuntu-based Linux**. It's also tested on a light-weight Ubuntu-variant LXLE distro. If you are interested in compiling from the source, instructions in [Compiling and Installing netgen](ADMIN.md) should help.

[Netgen](http://opencircuitdesign.com/netgen/) is a tool for comparing netlists, a process known as LVS, which stands for "Layout vs. Schematic". This is an important step in the integrated circuit design flow, ensuring that the geometry that has been laid out matches the expected circuit.
Netgen is currently maintained by Tim Edwards (opencircuitdesign.com/netgen)

## Table of Content
- [Downloading & Setting Up Netgen](#downloading-&-setting-up-netgen)
- [Quick Start Guide](#quick-start-guide)

## Downloading & Setting Up Netgen

- Change directory ```cd``` to install directory <INSTALL_DIR> e.g. ```/home/user/cad```
- To download from the ```git``` repository:
  - ```git clone https://github.com/silicon-vlsi-org/eda-netgen```
- Change directory to the installed `netgen` directory eg. ```cd eda-netgen```
- Checkout the desired version: ```git checkout v1.5.272```
  - To make sure you are on the right version type ```git branch``` and your output should have a line like this :
  - ```* (HEAD detached at v1.5.272)```

- Add the following environment variables in your `~/.bashrc`  

```bash
export NETGEN_HOME=<INSTALL_DIR>/eda-netgen/glnxa64
export PATH=$PATH:$NETGEN_HOME/bin
```

where `<INSTALL_DIR>` is the directory where `eda-netgen` is installed e.g. `/home/user/cad`

## Quick Start Guide
FIXME: Add examples to the repo

## Release History
- **v1.5.272**:
  - **Netgen 1.5.272** for **Ubuntu 22.04**
    - Compiled on linode VM running Ubuntu 22.04 kernel  5.15.0-100-generic #110-Ubuntu 03/10/24
  - **Netgen 1.5.219** for **CentOS7**
- **v1.5.185**:
  - **Netgen 1.5.185** for **Ubuntu 18.04**
    - Compiled on Linux AWS Lightsail **5.4.0-1049-aws** #51~**18.04.1-Ubuntu**
  - **Netgen 1.5.219** for **CentOS7**
