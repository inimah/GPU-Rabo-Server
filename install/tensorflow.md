* Download the source tensorflow-gpu

* For Python2.7

https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.2.0-cp27-none-linux_x86_64.whl

* For Python3

https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.2.0-cp34-cp34m-linux_x86_64.whl

* Install under your choice of python version / packages:

```
module load miniconda/2

python --version
Python 2.7.13 :: Continuum Analytics, Inc.

which python
/opt/sw/packages/miniconda/miniconda2/bin/python
```
* Install tensorflow after loading miniconda module
```
sudo pip install tensorflow_gpu-1.2.0-cp27-none-linux_x86_64.whl
```

