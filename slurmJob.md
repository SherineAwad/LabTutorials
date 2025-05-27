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



## ✅ SLURM Settings and Their Parallelism Implication

| SLURM Option               | Implies               | Usually Used For                                         |
|----------------------------|-----------------------|----------------------------------------------------------|
| `--nodes`                  | **Cluster distribution** | Number of physical machines (nodes) to allocate          |
| `--ntasks` / `--ntasks-per-node` | **Multiprocessing**    | Multiple processes (e.g., MPI, `srun`)                    |
| `--cpus-per-task`          | **Multithreading**     | One process using multiple threads (e.g., OpenMP, TBB)   |


## 🔁 Multiprocessing vs Multithreading

| Feature            | Multiprocessing                             | Multithreading                              |
|--------------------|---------------------------------------------|---------------------------------------------|
| **Definition**     | Running **multiple processes**              | Running **multiple threads** in one process |
| **Memory**         | Each process has its **own memory space**   | Threads **share the same memory space**     |
| **Communication**  | Slower – typically via MPI or sockets       | Faster – threads access shared memory       |
| **Failure**        | One process crash doesn't kill others       | Thread crash can bring down the whole process |
| **Used In**        | MPI, distributed computing, job arrays      | OpenMP, multithreaded C++/Java/Python       |
| **Overhead**       | Higher (process creation & context switch)  | Lower (lighter-weight than processes)       |


## 💡 Analogy

- **Multiprocessing**: Like having 12 cooks in **12 separate kitchens**. Each has their own space and tools. They work in parallel but don’t easily share food/tools (unless they go out of their way to do so).

- **Multithreading**: Like 12 cooks working in **one big kitchen**, sharing tools and ingredients, and able to collaborate faster — but if one causes a fire, the whole kitchen might go down.



# 🏭 Food Factory Analogy for SLURM Parallelism

This analogy compares SLURM job components to parts of a food production system to help understand nodes, tasks, CPUs, and threads.

---

## 🔧 Concept Mapping

| SLURM Concept      | Food Factory Analogy                     | Real Meaning                            |
|--------------------|------------------------------------------|-----------------------------------------|
| **Node**           | A **factory branch** (separate building) | A physical machine in the cluster       |
| **Task / Process** | A **kitchen** in a branch                | A process (e.g., MPI rank or `srun`)    |
| **CPU / Core**     | A **stove** in the kitchen               | A CPU core assigned to a task           |
| **Thread**         | A **cook** working on a stove            | A thread inside the process             |

---

## 🧠 Behavior and Coordination

| Situation                        | Analogy                                                  | Real Meaning                                |
|----------------------------------|-----------------------------------------------------------|---------------------------------------------|
| One kitchen uses 1 stove         | 1 cook using 1 stove                                      | Single-threaded process                     |
| One kitchen uses 4 stoves        | 4 cooks using 4 stoves (in same kitchen)                 | Multithreaded (e.g., 4 OpenMP threads)      |
| 3 kitchens in one branch         | 3 separate kitchens with their own stoves                | 3 processes on the same node                |
| Kitchens in different branches   | Kitchens in different buildings use remote communication | Inter-node communication (e.g., MPI)        |

---

## ✅ SLURM Mapping Example

```bash
#SBATCH --nodes=2               # 2 factory branches
#SBATCH --ntasks-per-node=3     # 3 kitchens per branch
#SBATCH --cpus-per-task=4       # 4 stoves per kitchen








