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
