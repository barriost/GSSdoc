# Class specification
Here are the per-class specification to run your containers on the Juliet machine of the ROMEO computing center. These are modification that are required for everything to go smoothly on our cluster and are different from teacher specifications.
To know the basics, connected to Juliet itself and know the advice for all containers, please refer to [this file](https://github.com/barriost/GSSdoc/blob/main/README.md)

# Monday, June 23rd

## __Welcome, Gray Scott Introduction, CPU Architecture, Vectorization VS Parallelization__
There is no container. Please follow teacher instructions. If running code is required, please make sure you're on a compute node.

## Compiler optimisation
Class : https://cta-lapp.pages.in2p3.fr/COURS/COMPILER_OPTIMISATION/index.html
Run container on Juliet: 
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
Run container on Juliet: 
```
apptainer shell /projects/m25065-students/containers/cpp_on_cpu.sif
```
OR
```
bash /projects/m25065-students/scripts/cpp_on_cpu.sh
```

## C++ 17/20/23 on CPU (and pyramid)
Class : https://cta-lapp.pages.in2p3.fr/COURS/PerformanceWithLayoutAndStencil
Run container on Juliet: 
```
apptainer shell /projects/m25065-students/containers/cpp_on_cpu.sif
```
OR
```
bash /projects/m25065-students/scripts/cpp_on_cpu.sh
```
# Wednesday, June 25th
## Performance with stencil in Sycl 
Class : https://gitlab.in2p3.fr/CodeursIntensifs/grayscott/
Run container on Juliet: 
```
apptainer shell /projects/m25065-students/containers/cpp_on_cpu.sif
```
OR
```
bash /projects/m25065-students/scripts/cpp_on_cpu.sh
```
*/!\ Juliet uses the Adaptive CPP version of the container. Please mention it if you report an issue to the teacher /!\\*

### Differences with the Adaptive CPP container
- The sycl-ls command does not exist
- Whenever you require `icpx` or `icpx-cuda`, use `acpp` instead
Example:
```
./coliru.bash acpp cpu
```

### Performance with stencil in Fortran
TBA

### Memory Profiling 
Class : 
Run container on Juliet: 
```
apptainer shell /projects/m25065-students/containers/mem_profiling.sif
```
OR
```
bash /projects/m25065-students/scripts/mem_profiling.sh
```  


## Thursday, June 26th
TBA

## Friday, June 27th
TBA

## Saturday, June 28th
TBA

## Sunday, June 29th
TBA

## Monday, June 30th
TBA

## Tuesday, July 1st
TBA

## Wednesday, July 2nd
TBA

## Thursday, July 3rd
TBA

## Friday, July 4th
TBA
