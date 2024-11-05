## Find Module
To list all available modules, run:
```
module avail
```
## Load Module
Load the modules you need, for instance,  load the Conda module first:
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
## Create Jupyter Notebook
To use the Jupyter interface, you need to install Jupyter Notebook or Jupyter Lab
```
module load miniconda
conda create -n env_name jupyter jupyter-lab
```
If you have installed or deleted a conda environment, run the following command in a terminal to update the Web Portal Access (OOD).
```
ycrc_conda_env.sh update
```
For creating an interactive Jupyter session using WebPortal please refer to [Interactive Web Portal Guildline]()
