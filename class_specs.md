# Class specification
Here are the per-class specification to run your containers on the Juliet machine of the ROMEO computing center. These are modification that are required for everything to go smoothly on our cluster and are different from teacher specifications.

For classes that were given on the previous days, see [this file.](https://github.com/barriost/GSSdoc/edit/main/passed_class_specs)

To know the basics, connected to Juliet itself and know the advice for all containers, please refer to [this file](https://github.com/barriost/GSSdoc/blob/main/README.md).

Reminder that all apptainer or bash commands need to be run on compute nodes.






# Thursday, July 3rd
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
### Load the correct libraries

Some libraries must be loaded by hand on Juliet. Please run these two commands to load them:

```
 source /apps/spack/spack/share/spack/setup-env.sh
```
and
```
 spack load cudnn@9.8.0.87-12
```

