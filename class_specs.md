# Class specification
Here are the per-class specification to run your containers on the Juliet machine of the ROMEO computing center. These are modification that are required for everything to go smoothly on our cluster and are different from teacher specifications.
To know the basics, connected to Juliet itself and know the advice for all containers, please refer to [this file](https://github.com/barriost/GSSdoc/blob/main/README.md).

Reminder that all apptainer or bash commands

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
Run container on Juliet (on a compute node):: 
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

## Performance with stencil in Fortran
TBA

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
Class: https://gitlab.in2p3.fr/grasland/grayscott-with-rust 

/!\ Apptainer is not recommended for the rust classes, we will be using podman. Remember the allocation request is different for podman

Run container on Juliet (on a compute node):: 
```
podman run --rm -it docker://gitlab-registry.in2p3.fr/grasland/numerical-rust-cpu/rust_light:latest /bin/bash
```
OR
```
bash /projects/m25065-students/scripts/rust.sh
```

# Friday, June 27th
## Python on CPU
Class: https://gitlab.in2p3.fr/alice.faure/gray-scott-python

This class uses Jupyter Lab, which will provide a web interface with the backend running on Juliet. You will need to use your own computer to visualize the interface.
We recommend you clone the repository before starting the container as the container does not include git.

### Start container and Jupyter lab on Juliet (on a compute node):

```
apptainer shell  --bind=/projects/m25065-students/scripts/jupyter_start.sh:/scripts/jupyter_start.sh /projects/m25065-students/containers/mem_profiling.sif
```
then start the jupyter lab container with the script we provided

```
bash /scripts/jupyter_start.sh
```
The script will open the jupyter lab on a port that isn't already in use. Note the number of the port

OR

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
TBA

# Tuesday, July 1st
TBA

# Wednesday, July 2nd
TBA

# Thursday, July 3rd
TBA

# Friday, July 4th
TBA
