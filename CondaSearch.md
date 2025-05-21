# Step 3: Search for a tool 

Once you isntalled and activated your conda enviroment, you can search for a tool to install as follows: 

```
conda search package 

```


## For example 

 ```bash 
conda search samtools 
```

Will show: 

```
Loading channels: done
# Name                       Version           Build  Channel             
samtools                      0.1.12               0  bioconda            
samtools                      0.1.12               1  bioconda            
samtools                      0.1.12               2  bioconda            
samtools                      0.1.13               0  bioconda            
samtools                      0.1.13               1  bioconda            
samtools                      0.1.14               0  bioconda            
samtools                      0.1.14               1  bioconda            
samtools                      0.1.15               0  bioconda            
samtools                      0.1.16               0  bioconda            
samtools                      0.1.17               0  bioconda            
samtools                      0.1.18               0  bioconda            
samtools                      0.1.18     h20b1175_12  bioconda            
samtools                      0.1.18     h270b39a_11  bioconda            
samtools                      0.1.18     h50ea8bc_13  bioconda            
samtools                      0.1.18     h96c455f_14  bioconda            
samtools                      0.1.18     hfb9b9cc_10  bioconda            
samtools                      0.1.19               0  bioconda            
samtools                      0.1.19               1  bioconda            
samtools                      0.1.19               2  bioconda            
samtools                      0.1.19               3  bioconda            
samtools                      0.1.19     h20b1175_10  bioconda            
samtools                      0.1.19      h270b39a_9  bioconda            
samtools                      0.1.19     h50ea8bc_11  bioconda            
samtools                      0.1.19      h94a8ba4_5  bioconda            
samtools                      0.1.19      h94a8ba4_6  bioconda  
```

To install a specific version and build use: 

`conda install -c channel package=Version=build`   

```bash
conda install -c bioconda samtools=0.1.19=h94a8ba4_6

