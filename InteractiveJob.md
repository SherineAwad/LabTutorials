## Requesting an Interactive Job on Greatlake

To start an interactive job on the **Greatlake** cluster using `salloc`, you can use the following command:

```bash
salloc --account=thahoang99 --nodes=1 --ntasks-per-node=1 --mem-per-cpu=50GB --cpus-per-task=2 --partition=standard --time=14:00:00
```

### Explanation of flags:

- `--account=thahoang99`: Specifies the account to charge for compute time.
- `--nodes=1`: Requests 1 compute node.
- `--ntasks-per-node=1`: Runs 1 task per node (useful for single-process jobs).
- `--mem-per-cpu=50GB`: Allocates 50GB of memory per CPU.
- `--cpus-per-task=2`: Requests 2 CPUs for your task (i.e., 1 task will use 2 CPUs).
- `--partition=standard`: Runs the job on the `standard` partition.
- `--time=14:00:00`: Maximum time for the job is 14 hours.

This command is suitable for launching an interactive session with high memory requirements on a single node.

