The default installation from Ubuntu 16.04 Repo are Python 2.7.12 and Python 3.5.2, but here we use separated modules to prevent clashing in some system utilities (which dependent to certain package version).

# Python 2.7.13

* Download from corresponding website: https://www.python.org/downloads/
* Untar and configure to /opt/sw/python
```
./configure --prefix=/opt/sw/tools/python/python-2.7.13 --enable-unicode=ucs4
sudo make
sudo make altinstall
```
# Python 3.5.3


# Python 3.6.0

