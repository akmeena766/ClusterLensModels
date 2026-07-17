# Cluster Lens Models

When we generate lens model, we run long chains ($>10^5$) to infer the posterior probability 
distribution function. This results in a few GBs of space for each lens model and sharing such 
large files is challenging. One way to circumvent this is sharing best-fit data products (such 
as potential, deflection, convergence, and shear) as high-resolution fits maps and error models
as low resolution fits maps. This might again lead to issue if we need to get error in high 
magnification regions.

Hence, instead of sharing the data products, we share the best-fit lens model itself and $10^3$ 
samples from the posterior distribution function with `burn_in=0.02` in a `.jld2` file. In 
addition, we also share the cluster galaxy, lensed image catalog, and input YAML file. In case
the user need to run their own lens models.


---
### File structure

Each folder in this repository containts lens modeling setup for a one galaxy cluster. And each 
folder contains four files:

1. [CLUSTER_NAME]_images.txt: Catalog of multiply lensed galxies.
2. [CLUSTER_NAME]_cluster_gals.txt: Catalog of cluster galaxy components.
3. [CLUSTER_NAME]_input.yaml: The YAML file containing full set-up used for modeling the cluster.
4. [CLUSTER_NAME]_sample.jld2: Contains best-fit model and 1000 posterior samples from the chain 
   (with 2% burn-in).


---
## Example scripts
1. BestFit.ipynb: This notebook demonstrats how to extract best-fit lens the model and calculate 
   various lensing quantities such as potential, deflection, convergence, and shear.
1. Errors.ipynb: This notebook demonstrats how to calculate errors based on the posterior samples.

---
## List of galaxy cluster
1. SMACS J0723.3-7327 ($z=0.387$)