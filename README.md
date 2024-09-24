# Libtorch_install
## 1. Install NVIDIA dirver
`sudo apt purge *nvidia*`

`sudo apt update`

`sudo apt upgrade`

`ubuntu-drivers list`

`sudo ubuntu-drivers install nvidia:560`

優先選擇使用nvidia gpu

`sudo prime-select nvidia`

## 2. Install CUDA
## 3. Install cudnn
## 4. Install cudatoolkit
## 5. Install up to date version of cmake
### donwload cmake file and extract
cmake website:
https://cmake.org/download/
### make file and install
`make ./configure`

`make -j8`

`sudo make install`

reference:
https://blog.csdn.net/qq21497936/article/details/141933927

## 	Do the cmake command with respect to absolute path to the PyTorch C++ API
`cmake -DCAFFE2_USE_CUDNN=True -DCMAKE_PREFIX_PATH=/home/ab123/libtorch/libtorch ..`

## 	Do the make command
`make`

##  	Run the code
`./main`
