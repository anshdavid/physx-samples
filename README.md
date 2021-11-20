PHYSX
=====

Containerized enviroment for running and building projects using Nvidia PhysX.

# Getting started

## Requierments

- [Docker](https://docs.docker.com/engine/)
- [NVIDIA Container Toolkit](https://github.com/NVIDIA/nvidia-docker)
- [NVIDIA PhysX SDK 4.1](https://github.com/NVIDIAGameWorks/PhysX)

# Setting up docker image and container

Dockerfile, build and run scripts can be downloaded from [here](https://github.com/ironWolf1990/containerized/tree/master/nvidia-opengl)

> Change the mount location in the `run.sh` script to the location where you have downloaded the nvidia physx repository

# Building PhysX

After clonning `NVIDIA PhysX SDK 4.1` repository, requirements for building PhysX can be found [here](https://gameworksdocs.nvidia.com/PhysX/4.1/documentation/platformreadme/linux/readme_linux.html). All these requirements are already included in the dockerfile provided

To build snippets examples - 
1. `cd PhysX/physx/ && chmod +x generate_projects.sh && ./generate_projects.sh`
2. `cd compiler/linux-release/ && make -j8`

## Running nvidia physx sample snippets
- `./runsnippets.sh`


# Common fixes (runnning in docker)

1. Update pyton to python3 in `PhysX/physx/generate_projects.sh`
2. Set clang version in `PhysX/physx/buildtools/cmake_generate_projects.py` if throws errors
3. Add flags [-Wno-suggest-destructor-override -Wno-suggest-override -Wno-reserved-identifier -Wno-unused-but-set-variable -Wno-dtor-name] to `PhysX/physx/source/compiler/cmake/linux/CMakeLists.txt` if throws errors.