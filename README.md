# Cluster Lens Models

When we generate lens model, we run long chains ($>10^5$) to infer the posterior probability 
distribution function. This results in a few GBs of space for each lens model and sharing such 
large files is challenging. One way to circumvent this is sharing best-fit data products (such 
as potential, deflection, convergence, and shear) as high-resolution fits maps and error models
as low resolution fits maps. This might again lead to issue if we need to get error in high 
magnification regions.

Hence, instead of sharing the data products, we share the best-fit lens model itself and $10^3$ 
samples from the posterior distribution function. 

---
This repository contains the YAML file for modeling galaxy clusters using LensFactory. Each folder
corresponds to a seperate galaxy cluster and contains four files:

1. [CLUSTER_NAME]_input.yaml: The YAML file for modeling the cluster
2. [CLUSTER_NAME]_images.txt: The imaging data for the cluster
3. [CLUSTER_NAME]_cluster_gals.txt: The source data for the cluster
4. [CLUSTER_NAME]_sample.jld2: The source images for the cluster

# List of galaxy cluster
1. SMACS J0723.3-7327 ($z=0.387$)