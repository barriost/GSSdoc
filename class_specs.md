# Class specification
Here are the per-class specification to run your containers on the Juliet machine of the ROMEO computing center. These are modification that are required for everything to go smoothly on our cluster and are different from teacher specifications.

For classes that were given on the previous days, see [this file.](https://github.com/barriost/GSSdoc/edit/main/passed_class_specs)

To know the basics, connected to Juliet itself and know the advice for all containers, please refer to [this file](https://github.com/barriost/GSSdoc/blob/main/README.md).

Reminder that all apptainer or bash commands need to be run on compute nodes.

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
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```
### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/eve_kiwaku.sif
```
OR
```
bash /projects/m25065-students/scripts/eve_kiwaku.sh
```


## C++17/20/23 on GPU with NVC++
Class: https://cta-lapp.pages.in2p3.fr/COURS/PerformanceWithLayoutAndStencil
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```
### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/cpp_on_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/cpp_on_gpu.sh
```


## Optimisation Cubic Root
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```

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
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```
Class: https://gitlab.in2p3.fr/CodeursIntensifs/grayscott/GrayScottSyclSetup/-/blob/main/README.md?ref_type=heads

Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/sycl_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/sycl_gpu.sh
```



## Performance with stencil in Fortran
Class : https://gitlab.in2p3.fr/lafage/GrayScottFortranTuto
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```
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
### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```
### Run container on Juliet (on a compute node):
```
apptainer shell --nv /projects/m25065-students/containers/rust_gpu.sif
```
OR
```
bash /projects/m25065-students/scripts/rust_gpu.sh
```  


# Thursday, July 3rd
## Python on GPU 
Class: https://gitlab.in2p3.fr/alice.faure/gray-scott-python

### Avoid GPU issues
To avoid issues with our MIG configuration, please run the following command after starting the srun

```
 [[ -n "$SLURM_STEP_GPUS" ]] && export CUDA_VISIBLE_DEVICES=$SLURM_STEP_GPUS || export CUDA_VISIBLE_DEVICES=$SLURM_JOB_GPUS
```

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

