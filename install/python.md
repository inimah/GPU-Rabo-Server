The default installation from Ubuntu 16.04 Repo are Python 2.7.12 and Python 3.5.2, but here we use separated modules to prevent clashing in some system utilities (which dependent to certain package version).

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
mkdir -p /opt/sw/modules/modulefiles/python
nano /opt/sw/modules/modulefiles/python/2.7.13
```
* with the content as follows:
```

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
nano /opt/sw/modules/modulefiles/python/3.5.3
```
with the content as follows:
```

```


# Python 3.6.0



* Create .modulerc for all python version (1 file for all version)
```
#%Module

# set version aliases and defaults.

if {![info exists python-done]} {

  module-version        python/2.7.12      default
  module-version        python/2.7.13      2.7.13
  set python-done 1

}

```
