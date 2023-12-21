`conda --version`
Get the current version of conda 

`conda update conda`
Update conda

`conda create --name snowflakes python=2.7`
Create a new environment named `snowflakes` with the Python version of 2.7

`conda activate snowflakes`
Activate the environment

`conda deactivate`
Deactivate current environment and puts into `base`

`conda info --envs`
List out all available environments created

`conda activate`
Get back to `base`

`conda remove --name snowflakes --all`
Removes the environment named `snowflakes` and everything inside it

`conda search beautifulsoup4`
To see if the module named `beautifulsoup4` is available from Anaconda repository

`conda install beautifulsoup4`
Install a module named `beautifulsoup4`

`conda list`
List all available/installed modules in current active environment

Python related:
`where python`
To show currently used python path

`python -m idlelib.idle`
Launch the IDLE from CLI 