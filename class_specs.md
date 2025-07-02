# Class specification
Here are the per-class specification to run your containers on the Juliet machine of the ROMEO computing center. These are modification that are required for everything to go smoothly on our cluster and are different from teacher specifications.

For classes that were given on the previous days, see [this file.](https://github.com/barriost/GSSdoc/edit/main/passed_class_specs)

To know the basics, connected to Juliet itself and know the advice for all containers, please refer to [this file](https://github.com/barriost/GSSdoc/blob/main/README.md).

Reminder that all apptainer or bash commands need to be run on compute nodes.



# Wednesday, July 2nd
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


# Thursday, July 3rd
## Python on GPU 
Class: https://gitlab.in2p3.fr/alice.faure/gray-scott-python


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

