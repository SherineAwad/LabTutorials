## Installing a Package with Conda

To install a package using Conda, use the following command:

```bash
conda install <package-name>
```

For example, to install **samtools** from the Bioconda channel:

```bash
conda install -c bioconda samtools
```

You can specify the channel before the package name if needed:

```bash
conda install bioconda::samtools
```


```bash
conda install -c bioconda samtools=0.1.19
```

