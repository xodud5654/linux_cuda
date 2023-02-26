# linux_cuda


sudo apt install nvidia-driver-525 nvidia-settings

sudo apt-get install dkms nvidia-modprobe

sudo apt update && sudo apt upgrade

sudo reboot

--------------------------------------------------------------------------------------------------------------------------------------
nvidia-smi

### cuda toolkit runfile 
example
wget https://developer.download.nvidia.com/compute/cuda/11.3.1/local_installers/cuda_11.3.1_465.19.01_linux.run
sudo sh cuda_11.3.1_465.19.01_linux.run

gedit ~/.bashrc

export PATH="/usr/local/cuda-11.0/bin:$PATH"
export LD_LIBRARY_PATH="/usr/local/cuda-11.0/lib64:$LD_LIBRARY_PATH"

source ~/.bashrc

nvcc -V

--------------------------------------------------------------------------------------------------------------------------------------
# anaconda install

bash Anaconda3-2022.10-Linux-x86_64.sh


--------------------------------------------------------------------------------------------------------------------------------------
#cudnn
다운로드 후 압축해제
sudo cp cudnn-*-archive/include/cudnn*.h /usr/local/cuda/include
sudo cp -P cudnn-*-archive/lib/libcudnn* /usr/local/cuda/lib64
sudo chmod a+r /usr/local/cuda/include/cudnn*.h /usr/local/cuda/lib64/libcudnn*

sudo nano ~/.bashrc
source ~/.bashrc

/usr/local/cuda-11.3/extras/demo_suite/deviceQuery

...
deviceQuery, CUDA Driver = CUDART, CUDA Driver Version = 12.0, CUDA Runtime Version = 11.3, NumDevs = 1, Device0 = NVIDIA GeForce RTX 3090 Ti
Result = PASS

conda create -n torch1121 python=3.8
conda activate torch1121
conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=11.3 -c pytorch


module error시
sudo add-apt-repository ppa:ubuntu-toolchain-r/test # Ignore if not ubuntu
sudo apt-get update
sudo apt-get install gcc-4.9
sudo apt-get upgrade libstdc++6
sudo apt-get dist-upgrade
strings /usr/lib/x86_64-linux-gnu/libstdc++.so.6 | grep GLIBCXX
