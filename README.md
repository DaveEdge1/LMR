# Last Millenium Reanalysis  

## Purpose
* This repo is designed specifically for use in PReSto. While other use cases may be practicable, we do not plan to support them here.
* This container utilizes the python package 'cfr' for paleoclimate data assimilation. For use of this product outside of PReSto, visit: '[LMR](https://fzhu2e.github.io/cfr/notebooks/lmr-cli.html)' by Feng Zhu and Julien Emile-Geay [Zhu et al., 2024](https://gmd.copernicus.org/articles/17/3409/2024/)

## How to run the container:
* launch docker on your local machine  
* open a shell and navigate to a directory: the directory needs the configs.yml file and a folder named recons  
* make any edits you wish to the configs.yml file  
* run 'docker pull davidedge/lipd_webapps:LMR' to download the container  
* run the following command: 'docker run -it -v "$(pwd)"/data:/data -v "$(pwd)"/recons:/recons -v "$(pwd)"/configs.yml:/configs.yml davidedge/lipd_webapps:LMR' 

## Exaplanation of command: 

* '-it' tells docker to show all the python output in your terminal (alternatively '-d' tells docker to run in the background)  
* there are 3 different 'volume mounts' which attach a file/directory outside the container to a counterpart within  
1. the data folder contains: iCESM_past1000historical/pr, iCESM_past1000historical/tas, and gistemp1200_GHCNv4_ERSSTv5 (the python script will download these files if they are not mounted)
2. the configs.yml is used to adjust various reconstruction parameters (a default file, as shown in this repo will be used if noone is mounted)
3. the recons folder contains the results. This mount is required to get data out, so you must have an empty directory called recons to point to 


See also: ([Hakim et al., 2016](https://doi.org/10.1002/2016JD024751); [Tardif et al., 2019](https://doi.org/https://doi.org/10.5194/cp-15-1251-2019))
