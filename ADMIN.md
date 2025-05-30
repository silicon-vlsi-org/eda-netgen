# ADMIN
This documentation is NOT for users, only if you are interested to compile, install and mange releases as done in this repo.

## Compiling and Installing Netgen for Ubuntu 22.04

**SETTING UP LINUX FOR COMPILE**

- Prepare for building netgen. 
- Base dev pkgs if not already installed ```sudo apt install build-essential linux-headers-‘uname -r‘```
- Some required packages if not already installed: **Tcl/Tk** (Ubuntu package names: ```tcl-dev, tk-dev```)
 
**USING SOURCE FROM GIT REPO**

- Compiled on linode VM running Ubuntu 22.04 kernel  5.15.0-100-generic #110-Ubuntu 03/10/24
- cd ```/home/ubuntu/sit-git-repos/eda-src```
- ```git clone git://opencircuitdesign.com/netgen```
- ```cd netgen```
- ```git checkout netgen-1.5```
- Configure: To see all configure options ```./configure -----help```. To install in root with all default options just type ```./configure```
- To install it in a user directory for eg. in ```$HOME/eda-bins/netgen```: 
```bash 
./configure --prefix=$HOME/eda-bins/netgen
```
- Make and install:
```bash
make
make install
```
- On successful compilation, the new compiled binaries/libs/should be in the target directory eg. ```$HOME/eda-bins/netgen```
  
- **IMPORTANT** If this install directory needs to be used by other users by copying the install directory, replace the absolute paths: eg. ```/home/vlsi/tools/netgen-15 -> $NETGEN_HOME```
- In the following files:
```bash
bin/netgen, lib/netgen/tcl/netgen.tcl
```
- Additionally, since the ```netgen.tcl``` is sourced from ```bin/netgen``` the environment variable needs to be passed by adding the following statement to ```netgen.tcl```:
```tcl
set NETGEN_HOME $::env(NETGEN_HOME)
```
- Set the environment variables as shown in [README.md](README.md)

**COMPILING FOR CENTOS**
- Follow the same steps as ngspice and magic

**CREATING A NEW RELEASE**

Check out this [doc](https://docs.github.com/en/github/administering-a-repository/releasing-projects-on-github/managing-releases-in-a-repository) in docs.github.com on how to create and manage releases.
  
- Check out the difference between the previous and current version: eg.
```bash
  diff -qr ~/eda-bins/netgen  <GIT-INSTALL_DIR>/eda-netgen/glnxa64
```
- Copy only the differences to the git repo, `add`, `commit` and `push` to the `github`.
  - **IMPORTANT** Make sure you backup the previous binaries in case you need it.
- Navigate to the main repo page eg. github.com/silicon-vlsi-org/eda-netgen
- To the right of the list of files, click **Create a new release** under the **Release** section.
- Tag the release version eg. ```v1.5.0```
  - The major release ```v1.5``` reflects the version of netgen.
  - The minor release ```vx.x.0``` reflects any changes done locally eg. examples, docs, etc.
- Do not add any binaries and do not select pre-release.
- Publish the release. 
- Now users can checkout this version eg. ```git checkout v8.3.0```
  
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


