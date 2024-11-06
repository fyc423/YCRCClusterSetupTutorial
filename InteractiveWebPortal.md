## Interactive Sessions
You can use the [Web Portal (Open OnDemand)](https://docs.ycrc.yale.edu/clusters-at-yale/access/ood/), and create an interactive session for the specific cluster you are using. This can be used during the development phase of your code for testing and troubleshooting. 

You can also use the web portal to 
- Check `Files` 
- Check active jobs under `Jobs`
- Check your user portal summary under `Utilities`

![WebProtal](https://github.com/fyc423/YCRCClusterSetupTutorial/blob/main/ood_welcome.png?raw=true)

To launch the server you will need to enter the following information:
- `Number of hours`: Sets the maximum wall time for this job. If the job exceeds this time, it will be automatically terminated. for `gpu_devel` partitions, the maximum number of hours is 6.
- `Number of CPU cores per node`: Requests number of nodes. If your job can run on multiple nodes (in a distributed fashion), you could adjust this number accordingly.
- `Memory per CPU core in GiB`: Allocates number of CPU cores for the job on the specified node. This is helpful for jobs that require parallel processing or multi-threading.
- `Partitions`: Specifies the partition. For the development phase, select `gpu_devel`.
- `Number of GPUs per node`: Requests the number of GB of memory per CPU core.

![PortalSetupl](https://github.com/fyc423/YCRCClusterSetupTutorial/blob/main/PortalSetup.JPG?raw=true)

This is equivalent to submitting an interactive job:
```
salloc --partition=gpu_devel --time=6:00:00 --nodes=1 --cpus-per-task=8 --mem-per-cpu=1g
```
- `partition`: Partitions

- `time`:  Number of hours

- `nodes`: Number of nodes

- `cpus-per-task`: Number of CPU cores per node

- `mem-per-cpu`: Memory per CPU core in GiB
