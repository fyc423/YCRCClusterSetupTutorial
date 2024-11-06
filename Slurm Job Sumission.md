Once your code is ready to run you can submit your script as a batch job. 
## Submission Script
Write a .sh script that specifies the resources required and commands to run. 
```
#!/bin/bash
#SBATCH --job-name=my_job               # Job name
#SBATCH --mail-type=FAIL,END            # Email if job fails or ends  
#SBATCH --mail-user=first.last@yale.edu # Your email address

#SBATCH --partition=gpu                 # Partition (queue) name, usually gpu
#SBATCH --nodes=1                       # Number of nodes
#SBATCH --ntasks=1                      # Number of tasks (usually 1 for GPU jobs)
#SBATCH --cpus-per-task=8               # Number of CPU cores per task
#SBATCH --mem-per-cpu=1G                # Memory per CPU core
#SBATCH --time=2-00:00:00               # Total run time (HH:MM:SS) For GPU, maximum time will be 2-00:00:00   
#SBATCH --gpus=a5000:1                  # Number and type of GPUs (if needed)

#SBATCH --output=logs/%x_%j.out         # Standard output file (%x for job name, %j for job ID)
#SBATCH --error=logs/%x_%j.err          # Standard error file

# Load necessary modules or software
module load python/3.8  # Example of loading Python module

# Activate your Conda environment (if using Conda)
source activate my_conda_env

# Run your program or script
python my_script.py --arg1 value1 --arg2 value2
```
You can upload the submission script directly to the desired folder via the web portal or using `scp` or `rsync`.

## Check Job Progress
To check your job status, you can access `Active Jobs` on the web portal. 
Or create an alias that shows job queue information for a user identified by NetID. 
```

To view output and error files after the job completes:
```
cat logs/%x_%j.out    # View output
cat logs/%x_%j.err   # View error
```
Or follow in real-time if the job is still running:
```
tail -f logs/%x_%j.out    # Follow output
tail -f logs/%x_%j.err   # Follow error
```
Or you can access the output and error files via the web portal.




