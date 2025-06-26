# Previous classes
This file contains classes from the previous days of the Gray Scott School. For the classes of the current/upcoming days, see [this file](https://github.com/barriost/GSSdoc/blob/main/class_specs.md)

# Monday, June 23rd

## __Welcome, Gray Scott Introduction, CPU Architecture, Vectorization VS Parallelization__
There is no container. Please follow teacher instructions. If running code is required, please make sure you're on a compute node.

## Compiler optimisation
Class : https://cta-lapp.pages.in2p3.fr/COURS/COMPILER_OPTIMISATION/index.html
Run container on Juliet (on a compute node): 
```
apptainer shell /projects/m25065-students/containers/compiler.sif
```
OR
```
bash /projects/m25065-students/scripts/compiler.sh
```

## Did you say Unit Testing ?
There is no container. Please follow teacher instructions. If running code is required, please make sure you're on a compute node.

# Tuesday, June 24th

## C++ 17/20/23 on CPU (and pyramid)
Class : https://cta-lapp.pages.in2p3.fr/COURS/PerformanceWithLayoutAndStencil
Run container on Juliet (on a compute node):: 
```
apptainer shell /projects/m25065-students/containers/cpp_on_cpu.sif
```
OR
```
bash /projects/m25065-students/scripts/cpp_on_cpu.sh
```

The source code for this class is inside the container at /home/Examples. It can be copied to your directory with the cp command

```
cp -r /home/Examples /path/to/the/desired/directory
```

# Wednesday, June 25th
## Performance with stencil in Sycl 
Class : https://gitlab.in2p3.fr/CodeursIntensifs/grayscott/

For this class, you need to clone the class from the Github, the container does not have them. You can do so from within the container.

Run container on Juliet (on a compute node):
```
apptainer shell /projects/m25065-students/containers/stencil_sycl.sif
```
OR
```
bash /projects/m25065-students/scripts/stencil_sycl.sh
```
*/!\ Juliet uses the Adaptive CPP version of the container. Please mention it if you report an issue to the teacher /!\\*

### Differences with the Adaptive CPP container
- The sycl-ls command does not exist
- Whenever you require `icpx` or `icpx-cuda`, use `acpp` instead
Example:
```
./coliru.bash acpp cpu
```

## Performance with stencil in Fortran
Class : https://gitlab.in2p3.fr/lafage/GrayScottFortranTuto

Run container on Juliet (on a compute node):
```
apptainer shell /projects/m25065-students/containers/stencil_fortran.sif
```
OR
```
bash /projects/m25065-students/scripts/stencil_fortran.sh
```  

## Memory Profiling 
Class : 
Run container on Juliet (on a compute node):: 
```
apptainer shell /projects/m25065-students/containers/mem_profiling.sif
```
OR
```
bash /projects/m25065-students/scripts/mem_profiling.sh
```  
