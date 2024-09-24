# Libtorch_install
## 1. Install NVIDIA dirver
```
sudo apt purge *nvidia*
sudo apt update`
sudo apt upgrade
ubuntu-drivers list
sudo ubuntu-drivers install nvidia:560
```
優先選擇使用nvidia gpu

`sudo prime-select nvidia`

## 2. Install CUDA
下載cuda安裝runfile

https://developer.nvidia.com/cuda-12-4-0-download-archive?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=20.04&target_type=runfile_local

下載cuda 12.4

`wget https://developer.download.nvidia.com/compute/cuda/12.4.0/local_installers/cuda_12.4.0_550.54.14_linux.run`

安裝
`sudo sh cuda_12.4.0_550.54.14_linux.run`

在bashrc裡面加入
  ```
  ##cuda 12.4
  export PATH=/usr/local/cuda/bin${PATH:+:${PATH}}  
  export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-12.4/lib64/
  export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH
  ```

## 3. Install cudnn
直接照著官方網站步驟

官網:

https://developer.nvidia.com/cudnn-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=20.04&target_type=deb_local

```
  wget https://developer.download.nvidia.com/compute/cudnn/9.4.0/local_installers/cudnn-local-repo-ubuntu2004-9.4.0_1.0-1_amd64.deb
  sudo dpkg -i cudnn-local-repo-ubuntu2004-9.4.0_1.0-1_amd64.deb
  sudo cp /var/cudnn-local-repo-ubuntu2004-9.4.0/cudnn-*-keyring.gpg /usr/share/keyrings/
  sudo apt-get update
  sudo apt-get -y install cudnn
```
用下面的指令可以確定是否正確安裝
`cat /usr/include/cudnn_version.h | grep CUDNN_MAJOR -A 2`

reference:

https://blog.csdn.net/weixin_45622961/article/details/136636431
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
