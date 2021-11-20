PHYSX
=====

### [REQUIREMENTS](https://gameworksdocs.nvidia.com/PhysX/4.1/documentation/platformreadme/linux/readme_linux.html)

### [DOCKERFILE](https://github.com/ironWolf1990/containerized/tree/master/nvidia-opengl)


# BUILD

1. `cd PhysX/physx/`
2. `chmod +x generate_projects.sh`
3. `./generate_projects.sh`
4. `cd compiler/linux-release/`
5. `make -j8`

# RUN SAMPLES
`./runsnippets.sh`


## COMMON FIXES (if runnning in docker)
1. Update pyton to python3 in `PhysX/physx/generate_projects.sh`
2. Set clang version in `PhysX/physx/buildtools/cmake_generate_projects.py` if throws errors
3. Add flags `PhysX/physx/source/compiler/cmake/linux/CMakeLists.txt` if throws errors based on your clang version. [-Wno-suggest-destructor-override -Wno-suggest-override -Wno-reserved-identifier -Wno-unused-but-set-variable -Wno-dtor-name]


