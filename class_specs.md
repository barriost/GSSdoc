# Class specification
Here are the per-class specification to run your containers on the Juliet machine of the ROMEO computing center. These are modification that are required for everything to go smoothly on our cluster and are different from teacher specifications.

For classes that were given on the previous days, see [this file.](https://github.com/barriost/GSSdoc/edit/main/passed_class_specs)

To know the basics, connected to Juliet itself and know the advice for all containers, please refer to [this file](https://github.com/barriost/GSSdoc/blob/main/README.md).

/!\ Remember that all apptainer or bash commands need to be run on compute nodes.


# Tuesday, June 30th
## Python on GPU 
Class: https://gitlab.in2p3.fr/alice.faure/gray-scott-python
We strongly recommend you clone the repository before starting the container as the container does not include git


### Run container on Juliet (on a compute node):
```
apptainer shell --nv --bind=/usr/local/cuda:/usr/local/cuda,/apps/:/apps/ --env LD_LIBRARY_PATH="/usr/local/cuda/targets/x86_64-linux/lib/:$LD_LIBRARY_PATH" /projects/m26116/containers/python_gpu.sif
```
OR
```
bash /projects/m26116/scripts/python_gpu.sh
```
### Adapt the files for the container.

Some files must be changed for the codes to work on the container:

In the GPU/cluster folder:

- You only need to run the `script_level3_in_apptainer.sh` with the path to `gray_scott_python` as the first argument and `/usr/local/cuda` as the second argument.
- Example of use, assuming you current directory is ~/gray_scott_python/GPU/cluster : `bash script_level3_in_apptainer.sh ~/gray_scott_python /usr/local/cuda`


# Wednesday, July 1st
## Fortran 2018 on GPU
Class : https://gitlab.in2p3.fr/lafage/GrayScottFortranTuto

### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m26166/containers/fortran_gpu.sif
```
OR
```
bash /projects/m26166/scripts/fortran_gpu.sh
```

/!\ To allow nvfortran to be recognized inside the container you might need to set the right environment variables by running `source` on the file at `Examples/GPU`

# Thursday, July 2nd
## Kokkos on GPU
Class : https://cta-lapp.pages.in2p3.fr/COURS/GRAY_SCOTT_REVOLUTIONS/GrayScott2026/web_2-26.html

### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m26166/containers/kokkos_gpu.sif
```
OR
```
bash /projects/m26166/scripts/kokkos_gpu.sh
```

