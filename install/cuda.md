## Following [NVDIA Documentation](http://docs.nvidia.com/cuda/cuda-installation-guide-linux/#axzz4VZnqTJ2A)
* Check dependencies and prerequisites:

* Verify pre-installation (if driver and toolkit have been installed)
```
lspci | grep -i nvidia
03:00.0 3D controller: NVIDIA Corporation Device 15f7 (rev a1)
82:00.0 3D controller: NVIDIA Corporation Device 15f7 (rev a1)
```

```
nvidia-smi
Wed Jun 21 07:30:43 2017       
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 375.51                 Driver Version: 375.51                    |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  Tesla P100-PCIE...  Off  | 0000:03:00.0     Off |                    0 |
| N/A   40C    P0    27W / 250W |      0MiB / 12193MiB |      0%      Default |
+-------------------------------+----------------------+----------------------+
|   1  Tesla P100-PCIE...  Off  | 0000:82:00.0     Off |                    0 |
| N/A   45C    P0    29W / 250W |      0MiB / 12193MiB |      4%      Default |
+-------------------------------+----------------------+----------------------+
                                                                               
+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID  Type  Process name                               Usage      |
|=============================================================================|
|  No running processes found                                                 |
+-----------------------------------------------------------------------------+

```

```
cat /proc/driver/nvidia/version

NVRM version: NVIDIA UNIX x86_64 Kernel Module  375.51  Wed Mar 22 10:26:12 PDT 2017
GCC version:  gcc version 5.4.0 20160609 (Ubuntu 5.4.0-6ubuntu1~16.04.4) 

```
* verify is toolkit is available (installed)
```
nvcc

The program 'nvcc' is currently not installed. You can install it by typing:
sudo apt install nvidia-cuda-toolkit

```
* Download kernel headers and development packages from Ubuntu page
```
done manually
```
* verify whether nouveau display driver is enabled (should be disable first) 
```
lsmod | grep nouveau
```
* Download cuda-toolkit from [NVIDIA](https://developer.nvidia.com/cuda-downloads)
* install cuda
```
sudo sh *.run
```

* install cuda-repo package (repository meta data)
```
sudo dpkg -i cuda-*.deb
```
### Apparently, In our case, CUDA driver is pre-installed but the path is unconfigured 
So, we need to add in global environment
```
export PATH=/usr/local/cuda-8.0/bin:$PATH
export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64:$LD_LIBRARY_PATH
```
So, alles goed! the rest is verifying the version
```
which nvcc
/usr/local/cuda-8.0/bin/nvcc

nvcc --version
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2016 NVIDIA Corporation
Built on Tue_Jan_10_13:22:03_CST_2017
Cuda compilation tools, release 8.0, V8.0.61

```


* Download NVIDIA CUDA® Deep Neural Network library (cuDNN) 
https://developer.nvidia.com/rdp/cudnn-download

