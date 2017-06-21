## Following [NVDIA Documentation](http://docs.nvidia.com/cuda/cuda-installation-guide-linux/#axzz4VZnqTJ2A)
* Check dependencies and prerequisites:
Download kernel headers and development packages from Ubuntu page
* Verify pre-installation (if driver and toolkit have been installed)
```
cat /proc/driver/nvidia/version
```
this will output
```
NVRM version: NVIDIA UNIX x86_64 Kernel Module  375.51  Wed Mar 22 10:26:12 PDT 2017
GCC version:  gcc version 5.4.0 20160609 (Ubuntu 5.4.0-6ubuntu1~16.04.4) 

```
* check is toolkit is available
```
nvcc
```
which result, in our system:
```
The program 'nvcc' is currently not installed. You can install it by typing:
sudo apt install nvidia-cuda-toolkit

```
* Download from [NVIDIA](https://developer.nvidia.com/cuda-downloads)
```
sudo dpkg -i cuda-*.deb
```
