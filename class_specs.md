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

## Sycl on GPU

Class: https://gitlab.in2p3.fr/CodeursIntensifs/grayscott/GrayScottSyclSetup/-/blob/main/README.md?ref_type=heads

Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/sycl_gpu_new.sif
```
OR
```
bash /projects/m25065-students/scripts/sycl_gpu.sh
```



## Performance with stencil in Fortran
Class : https://gitlab.in2p3.fr/lafage/GrayScottFortranTuto

### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/fortran_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/fortran_gpu.sh
```

# Wednesday, July 1st
## Rust on GPU:
Class:  https://gitlab.in2p3.fr/grasland/numerical-rust-gpu

### Run container on Juliet (on a compute node):
```
apptainer shell --nv --bind=/usr/share/glvnd/:/usr/share/glvnd/ --env VK_ICD_FILENAMES=/usr/share/glvnd/egl_vendor.d/10_nvidia.json rust_light_latest.sif
```
OR
```
bash /projects/m25065-students/scripts/rust_gpu.sh
```  
