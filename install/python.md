The default installation from Ubuntu 16.04 Repo are Python 2.7.12 and Python 3.5.2, but here we use separated modules to prevent clashes of some system utilities (which dependent to certain package version).

# Python 2.7.13

* Download from corresponding website: https://www.python.org/downloads/
* Untar and configure to /opt/sw/tools/python/python-2.7.13
```
sudo mkdir -p /opt/sw/tools/python/python-2.7.13
./configure --prefix=/opt/sw/tools/python/python-2.7.13 --enable-unicode=ucs4
sudo make
sudo make altinstall
```
* Create module file
```
sudo mkdir -p /opt/sw/modules/modulefiles/python
sudo nano /opt/sw/modules/modulefiles/python/2.7.13
```
* with the content as follows:
```
#%Module
set version 2.7.13

proc ModulesHelp { } {
  puts stderr "This module provides an version ${version} of the Python,"
  puts stderr "as an alternative to the operating system default version "
  puts stderr " 2.7.12 Python.\n"
  puts stderr ""
}

module-whatis "Adds Python 2.7.13 to PATH etc"

set prefix      /opt/sw/tools/python/python-${version}
prepend-path    PATH                ${prefix}/bin
prepend-path    LIBRARY_PATH        ${prefix}/lib
prepend-path    MANPATH             ${prefix}/share/man
prepend-path    PYTHONPATH          ${prefix}/lib/python2.7/site-packages
prepend-path    LD_LIBRARY_PATH     ${prefix}/lib/python2.7

setenv  PYTHON_DIR      ${prefix}
setenv  PYTHON_BIN      ${prefix}/bin
setenv  PYTHON_LIB      ${prefix}/lib
setenv  PYTHON_INC      ${prefix}/include
```

# Python 3.5.3

* Untar and configure to /opt/sw/tools/python/python-3.5.3
```
sudo mkdir -p /opt/sw/tools/python/python-3.5.3
./configure --prefix=/opt/sw/tools/python/python-3.5.3 --enable-unicode=ucs4
sudo make
sudo make altinstall
```
* Create module file
```
sudo nano /opt/sw/modules/modulefiles/python/3.5.3
```
with the content as follows:
```
#%Module
set version 3.5.3

proc ModulesHelp { } {
  puts stderr "This module provides an version ${version} of the Python,"
  puts stderr "as an alternative to the operating system default version "
  puts stderr " 2.7.12 Python.\n"
  puts stderr ""
}

module-whatis "Adds Python 3.5.3 to PATH etc"

set prefix      /opt/sw/tools/python/python-${version}
prepend-path    PATH                ${prefix}/bin
prepend-path    LIBRARY_PATH        ${prefix}/lib
prepend-path    MANPATH             ${prefix}/share/man
prepend-path    PYTHONPATH          ${prefix}/lib/python3/site-packages
prepend-path    LD_LIBRARY_PATH     ${prefix}/lib/python3

setenv  PYTHON_DIR      ${prefix}
setenv  PYTHON_BIN      ${prefix}/bin
setenv  PYTHON_LIB      ${prefix}/lib
setenv  PYTHON_INC      ${prefix}/include
```


# Python 3.6.0

* Create module file
```
sudo nano /opt/sw/modules/modulefiles/python/3.6.0
```
with the content as follows:

```
#%Module
set version 3.6.0

proc ModulesHelp { } {
  puts stderr "This module provides an version ${version} of the Python,"
  puts stderr "as an alternative to the operating system default version "
  puts stderr " 2.7.12 Python.\n"
  puts stderr ""
}

module-whatis "Adds Python 3.6.0 to PATH etc"

set prefix      /opt/sw/tools/python/python-${version}
prepend-path    PATH                ${prefix}/bin
prepend-path    LIBRARY_PATH        ${prefix}/lib
prepend-path    MANPATH             ${prefix}/share/man
prepend-path    PYTHONPATH          ${prefix}/lib/python3/site-packages
prepend-path    LD_LIBRARY_PATH     ${prefix}/lib/python3

setenv  PYTHON_DIR      ${prefix}
setenv  PYTHON_BIN      ${prefix}/bin
setenv  PYTHON_LIB      ${prefix}/lib
setenv  PYTHON_INC      ${prefix}/include
```

## Create .modulerc for all python version (1 file for all version)
```
#%Module

# set version aliases and defaults.

if {![info exists python-done]} {

  module-version        python/3.6.0      3.6
  module-version        python/3.5.3      3.5
  module-version        python/2.7.13      2.7
  module-version        python/2.7.12      default
    
  set python-done 1

}

```
