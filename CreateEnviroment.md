## Load Anaconda or Miniconda
After logging into the cluster, load the Conda module first:
```
module load anaconda3  # or `module load miniconda`
```
## Create a Conda Environment
Create a new Conda environment. Replace `myenv` with your desired environment name and specify any packages you need (e.g., `numpy`, `pandas`).
```
conda create --name myenv numpy pandas
```
To create an environment for your specific project. First create your project folder:
```
mkdir -p ~/project
```
Then create a new Conda environment in the specified prefix. Replace `<project_name>` with your desired name for the project:
```
conda create --prefix ~/project/<project_name> numpy pandas
```
