# Class specification
Here are the per-class specification to run your containers on the Juliet machine of the ROMEO computing center. These are modification that are required for everything to go smoothly on our cluster and are different from teacher specifications.

For classes that were given on the previous days, see [this file.](https://github.com/barriost/GSSdoc/edit/main/passed_class_specs)

To know the basics, connected to Juliet itself and know the advice for all containers, please refer to [this file](https://github.com/barriost/GSSdoc/blob/main/README.md).

Reminder that all apptainer or bash commands need to be run on compute nodes.


# Monday, June 29th
## C++ 20 Computing with Eve + Kiwaku
Class: https://events.codereckons.com/

### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/eve_kiwaku.sif
```
OR
```
bash /projects/m25065-students/scripts/eve_kiwaku.sh
```
### Compiling with Eve

Eve requires C++20 or later, you might need to add the option `-std=c++20` to the compiler.

## C++17/20/23 on GPU with NVC++
Class: https://cta-lapp.pages.in2p3.fr/COURS/PerformanceWithLayoutAndStencil

### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/cpp_on_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/cpp_on_gpu.sh
```
# Tuesday, June 30th
## Python on GPU 
Class: https://gitlab.in2p3.fr/alice.faure/gray-scott-python
We strongly recommend you clone the repository before starting the container as the container does not include git


### Run container on Juliet (on a compute node):
```
apptainer shell --nv --bind=/usr/local/cuda:/usr/local/cuda,/apps/:/apps/ --env LD_LIBRARY_PATH="/usr/local/cuda/targets/x86_64-linux/lib/:$LD_LIBRARY_PATH" /projects/m25065-students/containers/python_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/python_gpu.sh
```
### Adapt the files for the container.

Some files must be changed for the codes to work on the container:

In the GPU/cluster folder:

- We recommend you do not use the `apptainer run_gpu.sh` file. You can use `bash script_inside_apptainer.sh` directly inside the container.
- In `script_inside_apptainer.sh` replace the value of PREFIX with the absolute path of your `gray-scott-python` repository




# Wednesday, July 1st
## Fortran 2018 on GPU
Class : https://gitlab.in2p3.fr/lafage/GrayScottFortranTuto

### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/fortran_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/fortran_gpu.sh
```

# Thursday, July 2nd
## Kokkos on GPU
Class : https://cta-lapp.pages.in2p3.fr/COURS/GRAY_SCOTT_REVOLUTIONS/GrayScott2026/web_2-26.html

### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/kokkos_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/fortran_gpu.sh
```

