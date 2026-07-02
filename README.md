# Image Quantification 101

## Python Setup

To ensure a smooth start into the Python session at ZIDAS 2026 we require you to prepare a conda environment. A conda environment is a special directory which contains all required dependencies to run Python and follow the planned Python session. Luckily you don't have to create this environment by hand. We will use the conda package manager to build the environment. If you have anaconda or miniforge already installed on your computer you can skip the first part and directly move on to the environment creation. Otherwise follow the miniforge install instructions first.

### Install miniforge
Miniforge is our recommended environment manager for Python environments. Please download the version which fits your operation system from [here](https://github.com/conda-forge/miniforge?tab=readme-ov-file#download) and follow the respective install instructions:
* [Windows](https://github.com/conda-forge/miniforge?tab=readme-ov-file#windows)
* [MacOS with Homebrew](https://github.com/conda-forge/miniforge?tab=readme-ov-file#homebrew)
* [MacOS & Linux](https://github.com/conda-forge/miniforge?tab=readme-ov-file#windows)

On MacOS and Linux close the terminal and reopen a new one. On Windows look for `Miniforge Prompt` in the start menu. 

You should be able to type `conda` into your terminal/Miniforge Prompt and see the following output:
```
usage: conda [-h] [-v] [--no-plugins] [-V] COMMAND ...

conda is a tool for managing and deploying applications, environments and packages.

options:
  -h, --help          Show this help message and exit.
  -v, --verbose       Can be used multiple times. Once for detailed output, twice for INFO logging, thrice for DEBUG logging, four times for TRACE logging.
  --no-plugins        Disable all plugins that are not built into conda.
  -V, --version       Show the conda version number and exit.

commands:
  The following built-in and plugins subcommands are available.

  COMMAND
    activate          Activate a conda environment.
    clean             Remove unused packages and caches.
    compare           Compare packages between conda environments.
    config            Modify configuration values in .condarc.
    create            Create a new conda environment from a list of specified packages.
    deactivate        Deactivate the current active conda environment.
    doctor            Display a health report for your environment.
    env               See `conda env --help`.
    info              Display information about current conda install.
    init              Initialize conda for shell interaction.
    install           Install a list of packages into a specified conda environment.
    list              List installed packages in a conda environment.
    notices           Retrieve latest channel notifications.
    package           Create low-level conda packages. (EXPERIMENTAL)
    remove (uninstall)
                      Remove a list of packages from a specified conda environment.
    rename            Rename an existing environment.
    repoquery         Advanced search for repodata.
    run               Run an executable in a conda environment.
    search            Search for packages and display associated information using the MatchSpec format.
    update (upgrade)  Update conda packages to the latest compatible version.

```

### Create ZIDAS2026 Environment
Download this GitHub repository:
![download_zip](./git-download-zip.png)
1. Make sure that you have the zidas-2026 branch selected.
2. Click on the green `Code` button.
3. Click on `Download ZIP`.
4. Unpack the downloaded ZIP file.

From inside your open terminal or Minifroge Prompt change into the unpacked directory. If you extracted the setup material in your `Downloads` directory you would now change to `Downloads/imagequantification101-zidas-2026`.

__Windows:__ `cd Downloads\imagequantification101-zidas-2026`

__MacOS/Linux:__ `cd Downloads/imagequantification101-zidas-2026`

Now we can create the environment with conda from the `zidas2026_env.yaml` file. Run the following command:
```commandline
conda env create -f zidas2026_env.yaml
```

Executing this command might take some time, but once it finishes you should see the following:
```
Downloading and Extracting Packages:

Preparing transaction: done
Verifying transaction: done
Executing transaction: done
```

To verify that everything worked run the following two commands:
```
conda activate zidas2026
napari
```

This should open the napari viewer after a little bit of waiting time. 

To start working with the notebooks, either run:
```
jupyterlab
```
or
```
python3 -m jupyterlab
```

This will start the jupyter server and open a tab in your internet browser that will allow you to interact with the notebooks.

## Run in your browser

Alternatively, the tutorial notebooks can be run directly in your browser without setting up a local Python environment. Click the badge below to launch the tutorial directly in your browser via [JupyterLite](https://jupyterlite.readthedocs.io/en/latest/).

[![Launch JupyterLite](https://img.shields.io/badge/launch-JupyterLite-F37626?logo=jupyter&logoColor=white)](https://uhlmanngroup.github.io/imagequantification101/)

In this setup, no data is uploaded to the cloud and code is executed in your browser directly. If you modify the notebooks, the modifications will be saved in your browser's local storage. You can download them and also upload new notebooks or data to the environment. To work with a fresh copy, use private/incognito mode or clear the local browser storage.

This is a very convenient way to immediately get startedwith the notebooks. However, please note that JupyterLite is a limited environment and does not support all features of a full Python installation. For example, you cannot use napari in JupyterLite, therefore the napari notebook is not available in this version. JupyterLite also cannot read TIFF files that require `imagecodecs`, such as compressed TIFFs; the provided tutorial TIFFs are uncompressed and compatible.

## To cite
If you use the exercise notebooks from this tutorial, please acknowledge it as follows:

Uhlmann, V., Albert, M., Buchholz, T.-O., Fuster-Barceló, C., and Witz, G.  (2026). Image Quantification 101 Tutorial. github.com/uhlmanngroup/imagequantification101

## Further resources
* Miura, K. & Sladoje, N. (2020). Bioimage Data Analysis Workflows. doi.org/10.1007/978-3-030-22386-1
* Bankhead, P. (2022). Introduction to Bioimage Analysis. bioimagebook.github.io
* Holmes, S. & Huber, W. (2018). Modern Statistics for Modern Biology. www.huber.embl.de/msmb

## Acknowledgements
Part of the material from this tutorial was adapted from Paula Balcells' Bachelor Thesis work carried out in the Uhlmann group.
