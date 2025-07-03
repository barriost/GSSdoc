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
# Thursday, June 26th
## Rust on CPU 
Class: https://numerical-rust-cpu-81b2c3.pages.in2p3.fr/

/!\ Apptainer is not recommended for the rust classes, we will be using podman. Remember the allocation request is different for podman

Run container on Juliet (on a compute node): 
Place yourself on the desired directory and create the exercise directory
```
mkdir -p exercises
```
then run the podman container
```
podman run -it --rm -v "$(pwd)/exercises":/root/exercises gitlab-registry.in2p3.fr/grasland/numerical-rust-cpu/rust_light:latest
```
OR
```
bash /projects/m25065-students/scripts/rust.sh
```

# Friday, June 27th
## Python on CPU
Class: https://gitlab.in2p3.fr/alice.faure/gray-scott-python

This class uses Jupyter Lab, which will provide a web interface with the backend running on Juliet. You will need to use your own computer to visualize the interface.
We **strongly** recommend you clone the repository before starting the container as the container does not include git.

### Start container and Jupyter lab on Juliet (on a compute node):

- You can use Apptainer to start the container

  ```
  apptainer shell  --bind=/projects/m25065-students/scripts/jupyter_start.sh:/scripts/jupyter_start.sh /projects/m25065-students/containers/mem_profiling.sif
  ```
  then start the jupyter lab container with the script we provided
  
  ```
  bash /scripts/jupyter_start.sh
  ```
  The script will open the jupyter lab on a port that isn't already in use. Note the number of the port

OR

- Alternatively, you can use our script:
  
  ```
  bash /projects/m25065-students/scripts/python_cpu.sh
  ```

### Access the notebook from your own laptop computer (ON YOUR OWN MACHINE)

Once you get Jupyter running, you will see a line starting with ` http://localhost:8xxx/lab?token=`
Note the 8xxx number and the line (token included)

First open a terminal **ON YOUR LOCAL MACHINE** (ex: with PowerShell if you are using Windows) and enter the command:

```
 ssh -N -L 8xxx:julietX:8xxx m25065-studxx@juliet.mesonet.fr
```
Replace the xx by the right values:
- `8xxx` the port number you got earlier
- `julietX` the node you've started the container on
- `m25065-studxx` your username on Juliet

Finally, open your web browser and copy/paste the entire ` http://localhost:8xxx/lab?token=...` line.
The jupyter interface should open soon.

In case of any issue, do not hesitate to ask for help in the #romeo-support channel of the Gray Scott School Discord Server

# Monday, June 30th
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


## Optimisation Cubic Root


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

