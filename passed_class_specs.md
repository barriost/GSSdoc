# Previous classes
This file contains classes from the previous days of the Gray Scott School. For the classes of the current/upcoming days, see [this file](https://github.com/barriost/GSSdoc/blob/main/class_specs.md)


# Monday, June 29th
## C++ 20 Computing with Eve
Class: https://events.codereckons.com/

### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m26166/containers/eve.sif
```
OR
```
bash /projects/m26166/scripts/eve.sh
```
### Compiling with Eve

Eve requires C++20 or later, you might need to add the option `-std=c++20` to the compiler.

To void errors we recommend using the following options for the compilation `-O3 -std=c++20 -DNDEBUG -march=native`

## C++17/20/23 on GPU with NVC++
Class: https://cta-lapp.pages.in2p3.fr/COURS/PerformanceWithLayoutAndStencil

### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m26166/containers/cpp_on_gpu.sif
```
OR
```
bash /projects/m26166/scripts/cpp_on_gpu.sh
```
