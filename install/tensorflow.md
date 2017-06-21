*) in Anaconda2 packages, this source-based installed tensorflow and keras only works under IPython environment (due to dependency between module and python interpreter)

* Download the source tensorflow-gpu

https://pypi.python.org/pypi/tensorflow-gpu/1.2.0
```
tensorflow_gpu-1.2.0-cp27-cp27mu-manylinux1_x86_64.whl
```

* Or
```
https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.2.0-cp27-none-linux_x86_64.whl
https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.2.0-cp34-cp34m-linux_x86_64.whl
```

* Install under your choice of python version / packages:

```
module load anaconda/2

python --version
Python 2.7.13 :: Anaconda 4.4.0 (64-bit)

which python
/opt/sw/packages/anaconda/anaconda2/bin/python
```
* Install tensorflow after loading anaconda module
```
pip install tensorflow_gpu-1.2.0-cp27-cp27mu-manylinux1_x86_64.whl
```

