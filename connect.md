## Connecting to Great Lakes via SSH

To connect to the **Great Lakes** HPC cluster from your terminal, use the following command:

```bash
ssh yourusername@greatlakes.arc-ts.umich.edu
```

Replace `yourusername` with your actual UMich username.  
Once connected, you’ll be in the login node where you can submit jobs, manage files, or load environments.

> **Note**: Avoid running heavy computations on the login node—use `salloc` or `sbatch` to run jobs on compute nodes.


