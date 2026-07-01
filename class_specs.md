# Class specification
Here are the per-class specification to run your containers on the Juliet machine of the ROMEO computing center. These are modification that are required for everything to go smoothly on our cluster and are different from teacher specifications.

For classes that were given on the previous days, see [this file.](https://github.com/barriost/GSSdoc/edit/main/passed_class_specs)

To know the basics, connected to Juliet itself and know the advice for all containers, please refer to [this file](https://github.com/barriost/GSSdoc/blob/main/README.md).

/!\ Remember that all apptainer or bash commands need to be run on compute nodes.


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
The course files are inside the container. We recommand you copy them to your home (this can be done from inside the container) before working to prevent any data loss.

