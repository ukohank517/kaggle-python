
## How to create environment

1. DL miniconda install script.

    - Go to[miniconda](https://docs.conda.io/en/latest/miniconda.html).

    - Since my OS is M1 Mac, so I choose `Miniconda3 macOS Apple M1 64-bit bash`. Then I get a script named `Miniconda3-latest-MacOSX-arm64.sh`

      ``` bash
      $ ls ~/Download
      # Miniconda3-latest-MacOSX-arm64.sh
      ```

2. Install miniconda:

    - Run the install script(use all default setting):

        ``` bash
        $ bash ~/Download/Miniconda3-latest-MacOSX-arm64.sh
        ```

    - Then check the paths for conda and python to confirm installation:
        ``` bash
        $ which conda
        # /Users/{user_name}/miniconda3/condabin/conda
        $ which python3
        # /Users/{user_name}/miniconda3/bin/python3
        ```

3. Create running environemt:

    - Create a miniconda's environment profile for Machine Learning(answer `y` to confirm the package installlation):
        ``` bash
        $ conda create -n conda_ML python=3.9 # newest
        ```

    - Check environment profiles:
        ```bash
        $ conda info -e
        ## conda environments:
        ##
        #base                  *  /Users/{user_name}/miniconda3
        #conda_ML                 /Users/{user_name}/miniconda3/envs/conda_ML

        #(base)
        ```
        As the terminal output, we can know we have 2 profiles and the default profile named `base` is now activated.

    - Change the profile to `conda_ML`
        ``` bash
        $ conda activate conda_ML # change to
        $ conda info -e
        ## conda environments:
        ##
        #base                     /Users/{user_name}/miniconda3
        #conda_ML              *  /Users/{user_name}/miniconda3/envs/conda_ML

        #(conda_ML)
        ```
        Now the conda profile is `conda_ML`.

4. Install tool package and kernel:
    ``` bash
    $ pip install jupyter notebook
    $ conda install notebook ipykernel
    $ ipython kernel install --user --name ML --display-name ML
    ```