## How to run the container:
* launch docker on your local machine  
* open a shell and navigate to a directory: the directory needs the configs.yml file and a directory named recons  
* make any edits you wish to the configs.yml file  
* run 'docker pull davidedge/lipd_webapps:LMR' to download the container  
* run the following command: 'docker run -it -v "$(pwd)"/data:/data -v "$(pwd)"/recons:/recons -v "$(pwd)"/configs.yml:/configs.yml davidedge/lipd_webapps:LMR' 

Exaplanation of command: 

* '-it' tells docker to show all the python output in your terminal (alternatively '-d' tells docker to run in the background)  
* there are 3 different 'volume mounts' which attach a file/directory outside the container to a counterpart within  
1. the data folder contains: iCESM_past1000historical/pr, iCESM_past1000historical/tas, and gistemp1200_GHCNv4_ERSSTv5 (the python script will download these files if they are not mounted)
2. the configs.yml is used to adjust various reconstruction parameters (a default file, as shown in this repo will be used if noone is mounted)
3. the recons folder contains the results. This mount is required to get data out, so you must have an empty directory called recons to point to 
