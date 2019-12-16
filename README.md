# Parco2019_baseline 

The code is to run interactive Molecular Dynamics (MD) simulations supervised by convolutional variational neural network (CVAE) as presented in [Parco2019]() conference. 

## Step to run workflow 

1. Prior to every run, if you want to clean up the jobs on the GPU, and stop the running `rabbitmq-server` and `celery` workers, run the bash script 

   ```bash 
   bash prerun_clean.sh 
   ```

   The workflow automatically draft all available GPUs of the system, but currently only support for one-node job. 

3. After everything is clear, the program can be run with 

   ```python 
   python cvae_md.py
   ```
   
   NOTE: For a new system other than the example, it requires the same inputs as an MD simulation, a xyz file, a topology file and a simulation setup. New simulation can be added in `omm_sim/openmm_simulation.py` or modified base on the existing case. Then a callable for the simulation setup needs to be created in `task.py`. 

## Dependencies 

A container that was tested with the workflow can be requested from the author. 