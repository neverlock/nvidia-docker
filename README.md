# NVIDIA Docker

This repository includes utilities to build and run NVIDIA Docker images.

![nvidia-gpu-docker](https://cloud.githubusercontent.com/assets/3028125/12213714/5b208976-b632-11e5-8406-38d379ec46aa.png)

> Example of how CUDA integrates with Docker

# Documentation

The full documentation is available on the [repository wiki](https://github.com/NVIDIA/nvidia-docker/wiki).  
A good place to start is to understand [why NVIDIA Docker](https://github.com/NVIDIA/nvidia-docker/wiki/Why%20NVIDIA%20Docker) is needed in the first place.

# Quick start

Assuming the NVIDIA drivers and Docker are properly installed (see [installation](https://github.com/NVIDIA/nvidia-docker/wiki/Installation))

#### _Ubuntu distributions_
```sh
# Install nvidia-docker and nvidia-docker-plugin
wget -P /tmp https://github.com/NVIDIA/nvidia-docker/releases/download/v1.0.1/nvidia-docker_1.0.1-1_amd64.deb
sudo dpkg -i /tmp/nvidia-docker*.deb && rm /tmp/nvidia-docker*.deb

# Test nvidia-smi
nvidia-docker run --rm nvidia/cuda nvidia-smi
```

#### _CentOS distributions_
```sh
# Install nvidia-docker and nvidia-docker-plugin
wget -P /tmp https://github.com/NVIDIA/nvidia-docker/releases/download/v1.0.1/nvidia-docker-1.0.1-1.x86_64.rpm
sudo rpm -i /tmp/nvidia-docker*.rpm && rm /tmp/nvidia-docker*.rpm
sudo systemctl start nvidia-docker

# Test nvidia-smi
nvidia-docker run --rm nvidia/cuda nvidia-smi
```

#### _Other distributions_
```sh
# Install nvidia-docker and nvidia-docker-plugin
wget -P /tmp https://github.com/NVIDIA/nvidia-docker/releases/download/v1.0.1/nvidia-docker_1.0.1_amd64.tar.xz
sudo tar --strip-components=1 -C /usr/bin -xvf /tmp/nvidia-docker*.tar.xz && rm /tmp/nvidia-docker*.tar.xz

# Run nvidia-docker-plugin
sudo -b nohup nvidia-docker-plugin > /tmp/nvidia-docker.log

# Test nvidia-smi
nvidia-docker run --rm nvidia/cuda nvidia-smi
```

# Issues and Contributing

**A signed copy of the [Contributor License Agreement](https://raw.githubusercontent.com/NVIDIA/nvidia-docker/master/CLA) needs to be provided to digits@nvidia.com before any change can be accepted.**

* Please let us know by [filing a new issue](https://github.com/NVIDIA/nvidia-docker/issues/new)
* You can contribute by opening a [pull request](https://help.github.com/articles/using-pull-requests/)
