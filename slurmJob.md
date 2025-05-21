## Submitting a Bash Script Job to Slurm

To run a bash script as a batch job on **Greatlake** using Slurm, you can use a script like the following:

```bash
#!/bin/bash
#SBATCH --job-name=SP                     # Name of the job
#SBATCH --nodes=1                         # Request 1 compute node
#SBATCH --ntasks-per-node=1              # 1 task per node
#SBATCH --cpus-per-task=1                # 1 CPU per task
#SBATCH --time=6:00:00                   # Time limit (6 hours)
#SBATCH --mem=30000                      # Memory request (in MB)
#SBATCH --partition=standard            # Partition name
#SBATCH --mail-type=END                 # Get email when the job ends
#SBATCH --mail-user=sherinem@umich.edu  # Your email address
#SBATCH --account=thahoang99            # Account name for billing

conda activate archr                     # Activate the conda environment
# Your commands go here                 # Add the commands you want to run below this line

```

### How to submit this script

1. Save the script to a file, for example: `run_job.sh`
2. Submit it to Slurm using:
   ```bash
   sbatch run_job.sh
   ```

This script requests a single node with 1 CPU, 30 GB of memory, and runs for up to 6 hours. It also sends you an email when the job finishes and activates the `archr` conda environment before running any subsequent commands (which you'd add after the `conda activate` line).


