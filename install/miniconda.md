
* download and install source miniconda
```
chmod +x Miniconda2-latest-Linux-x86_64.sh
sudo ./Miniconda2-latest-Linux-x86_64.sh

```
* use /opt/sw/packages/miniconda/miniconda2 as prefix or destination directory to install miniconda2
```
Miniconda2 will now be installed into this location:
/home/tita/miniconda2

  - Press ENTER to confirm the location
  - Press CTRL-C to abort the installation
  - Or specify a different location below

[/home/tita/miniconda2] >>> /opt/sw/packages/miniconda/miniconda2
PREFIX=/opt/sw/packages/miniconda/miniconda2
installing: python-2.7.13-0 ...
installing: asn1crypto-0.22.0-py27_0 ...

```
* and last step of installation
```
Do you wish the installer to prepend the Miniconda2 install location
to PATH in your /home/tita/.bashrc ? [yes|no]
[no] >>> no

```
* create module
```
sudo mkdir -p /opt/sw/modules/modulefiles/miniconda
sudo nano /opt/sw/modules/modulefiles/miniconda/2
```
* content of module file
```
#%Module
set version 2

proc ModulesHelp { } {
        puts stderr "This module provides Miniconda with Python version ${version}."
        puts stderr "This Miniconda is installed specifically for researches that use"
        puts stderr "Deep Learning packages such as: Theano, TensorFlow, and Keras."
}

module-whatis "Add Miniconda with Python version ${version} for Deep Learning to the PATH"

set prefix	/opt/sw/packages/miniconda/miniconda${version}
prepend-path    PATH            ${prefix}/bin
prepend-path    LIBRARY_PATH    ${prefix}/lib
prepend-path    MAN_PATH        ${prefix}/share/man
prepend-path    PYTHON_PATH     ${prefix}/lib/python2.7
prepend-path    PACKAGES_PATH   ${prefix}/lib/python2.7/site-packages

setenv  PYTHON_DIR	${prefix}
setenv  PYTHON_BIN	${prefix}/bin
setenv  PYTHON_LIB	${prefix}/lib
setenv  PYTHON_INC	${prefix}/include
```
* create .modulerc
```
sudo nano /opt/sw/modules/modulefiles/miniconda/.modulerc
```
* and the content
```
#%Module
# set version aliases and defaults.
if {![info exists miniconda-done]} {
        module-version  miniconda/2                default
        set miniconda-done 1
}
```
