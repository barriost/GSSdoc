# Class specification
Here are the per-class specification to run your containers on the Juliet machine of the ROMEO computing center. These are modification that are required for everything to go smoothly on our cluster and are different from teacher specifications.

For classes that were given on the previous days, see [this file.](https://github.com/barriost/GSSdoc/edit/main/passed_class_specs)

To know the basics, connected to Juliet itself and know the advice for all containers, please refer to [this file](https://github.com/barriost/GSSdoc/blob/main/README.md).

Reminder that all apptainer or bash commands need to be run on compute nodes.

# Monday, June 30th
## C++ 20 Computing with Eve + Kiwaku
Class: https://events.codereckons.com/
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```
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
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```
### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/cpp_on_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/cpp_on_gpu.sh
```


## Optimisation Cubic Root
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```

Class: https://cta-lapp.pages.in2p3.fr/COURS/OPTIMISATION_RACINE_CUBIQUE/

### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/cubic_root.sif
```
OR
```
bash /projects/m25065-students/scripts/cubic_root.sh
```


# Tuesday, July 1st

## Sycl on GPU
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```
Class: https://gitlab.in2p3.fr/CodeursIntensifs/grayscott/GrayScottSyclSetup/-/blob/main/README.md?ref_type=heads

Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/sycl_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/sycl_gpu.sh
```



## Performance with stencil in Fortran
Class : https://gitlab.in2p3.fr/lafage/GrayScottFortranTuto
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```
### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/fortran_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/fortran_gpu.sh
```



# Wednesday, July 2nd
## Rust on GPU:
Class:  https://gitlab.in2p3.fr/grasland/numerical-rust-gpu
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```
### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/rust_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/rust_gpu.sh
```  


# Thursday, July 3rd
## Python on GPU 
Class: https://gitlab.in2p3.fr/alice.faure/gray-scott-python

### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```

### Run container on Juliet (on a compute node):
```
apptainer shell --nv --bind=/usr/local/cuda:/usr/local/cuda,/apps/:/apps/ /projects/m25065-students/containers/python_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/python_gpu.sh
```
### Load the correct libraries

Some libraries must be loaded by hand on Juliet. Please run these two commands to load them:

```
 source /apps/spack/spack/share/spack/setup-env.sh
```
and
```
 spack load cudnn@9.8.0.87-12
```

