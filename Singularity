Bootstrap: docker
From: nvidia/cuda:11.0-cudnn8-devel-ubuntu18.04

%labels
  Author CaLLUM wALLEY

%environment
  SHELL=/bin/bash

  # add CUDA paths
  CPATH="/usr/local/cuda/include:$CPATH"
  PATH="/usr/local/cuda/bin:$PATH"
  LD_LIBRARY_PATH="/usr/local/cuda/lib64:$LD_LIBRARY_PATH"
  CUDA_HOME="/usr/local/cuda"

  export PATH LD_LIBRARY_PATH CPATH CUDA_HOME

%post
  VOLSUNG_VER=1.13.1
  
  
  apt-get update
  apt-get install -yq \
    cmake \
    make \
    curl \
    git \
    wget \
    vim

  wget https://s3.amazonaws.com/volsung-install-files/volsung-LinuxMint-19.1-v$VOLSUNG_VER.tar.gz
  tar -xvf volsung-LinuxMint-19.1-v$VOLSUNG_VER.tar.gz
  cd volsung-LinuxMint-19.1-v$VOLSUNG_VER
  ./init-ubuntu-18-04
  ./init-ubuntu-remote-18-04
  ./setup-ubuntu-18-04

rm -rf volsung-LinuxMint-19.1-v$VOLSUNG_VER.tar.gz
echo "Yay!"
 # echo "\n #Cuda paths \n" >> /environment
 # echo 'export CPATH="/usr/local/cuda/include:$CPATH"' >> /environment
 # echo 'export PATH="/usr/local/cuda/bin:$PATH"' >> /environment
 # echo 'export LD_LIBRARY_PATH="/usr/local/cuda/lib64:$LD_LIBRARY_PATH"' >> /environment
 # echo 'export CUDA_HOME="/usr/local/cuda"' >> /environment
