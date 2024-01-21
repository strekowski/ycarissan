# Advanced slurm

## Intro

Up to date state of the queue :
```
watch squeue -u yannick
```

## Interactive sessions

Running an interactive session :

```
srun --pty /bin/bash -i
```
## Dependencies

```
sbatch --dependency=<type:job_id[:job_id][,type:job_id[:job_id]]> ...
```

 * after:jobid[:jobid...] 	job can begin after the specified jobs have started
 * afterany:jobid[:jobid...] 	job can begin after the specified jobs have terminated
 * afternotok:jobid[:jobid...] 	job can begin after the specified jobs have failed
 * afterok:jobid[:jobid...] 	job can begin after the specified jobs have run to completion with an exit code of zero (see the user guide for caveats).
 * singleton 	jobs can begin execution after all previously launched jobs with the same name and user have ended. This is useful to collate results of a swarm or to send a notification at the end of a swarm.


## Arrays