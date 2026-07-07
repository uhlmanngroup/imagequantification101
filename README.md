# Image Quantification 101

## Python Setup

The Python session requires the installation of a few Python packages on your machine. The best way to do this is to use a package manager that will create a safe *environment* ensuring that your installation for the course will be isolated from your other Python installations. We offer here two choices of package/environment managers: either conda or pixi. Both systems have their advantages. Conda is more widely used but sometimes a bit more difficult to install. Pixi is easier to install and offers an optimal way to manage package installation but is a bit less popular as it's newer. If you already used conda and are familiar with it, you don't have to change. If you want to discover something new or have no experience with conda, we recommend to use pixi. The following instructions will guide you through the installation of either conda or pixi and the creation of a Python environment for the course.

### pixi
Pixi is a new package manager for Python that is easy to install and use. To install it you need to run a single command line in your terminal. 

#### MacOS and Linux
For MacOS users, just look for the Terminal application in the `Applications/Utilities` folder. For Linux users, open your preferred terminal application. Then just type the following command and hit enter:
```
curl -fsSL https://pixi.sh/install.sh | sh
```
Upon closing and reopening the terminal, you should be able to type `pixi` and see some output about pixi usage.

#### Windows
For Windows users, open the `Powershell Terminal`. Then just type the following command and hit enter:

```
powershell -ExecutionPolicy Bypass -c "irm -useb https://pixi.sh/install.ps1 | iex"
```

Upon closing and reopening the Powershell terminal, you should be able to type `pixi` and see some output about pixi usage. **If you get an error message about the execution policy, try to open the alternative terminal called `Command Prompt`. If that fails try to run one of the terminal in Admin mode (right click on the app and select run as admin).**

#### Using pixi

Pixi is folder based, meaning that you will install packages in a given folder. For the course, we want to use the course repository. So download this repository (green button at the top left) and unzip it (on Windows, ensure that you actually extract the files).

![download_zip](./git-download-zip.png)

Then, in your terminal, move to that folder using the `cd` command. If you are not sure of the exact path to the folder, you can drag and drop the folder into the terminal window and it will fill in the path for you.

```
cd path/to/imagequantification101-zidas-2026
```

We provide a `pixi.toml` and a `pixi.lock` file in the repository. These files contain the information about the packages that we need for the course. To install them, just type the following command and hit enter:
```
pixi install --frozen
```

Now you can launch tools that were installed by pixi. The two that we will need are `napari ` and `jupyterlab`. You can launch them by typing the following commands:
```
pixi run napari
```
```
pixi run jupyterlab
```
You can run multiple tools at the same time in different terminal windows. Just remember to always first move to the folder containing your environment!

#### Your own pixi environment
If you want to create your own pixi environment, you can do so by running the following command in the folder where you want to create the environment:

```
pixi init
```
This will create a `pixi.toml` file in that folder. You can then add packages to that file and run `pixi install` to install them. You can also use `pixi run <tool>` to run any tool that you installed in that environment.

For example to install napari and jupyterlab in your own environment, you can run the following commands:

```
pixi add napari pyqt6 jupyterlab
```

The tools will become available in that folder AND the packages will be automatically listed in the `pixi.toml` file allowing you to recreate the environment later on another machine. You can also share the `pixi.toml` file with others to allow them to recreate your environment.

### Install miniforge

Miniforge is our recommended conda environment manager. Please download the version which fits your operating system from [here](https://github.com/conda-forge/miniforge?tab=readme-ov-file#download) and follow the respective install instructions:
* [Windows](https://github.com/conda-forge/miniforge?tab=readme-ov-file#windows)
* [MacOS with Homebrew](https://github.com/conda-forge/miniforge?tab=readme-ov-file#homebrew)
* [MacOS & Linux](https://github.com/conda-forge/miniforge?tab=readme-ov-file#unix-like-platforms-macos-linux--wsl)

On Windows you can step through the installer instructions. On MacOS and Linux you can run:
```
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
```

to download the installer and then execute it using the following command:

```
bash Miniforge3-$(uname)-$(uname -m).sh
```

and step through the instructions in the terminal (just keep on hitting Enter to go through the license). You can accept the default options **except** for the last question which asks you `Proceed with initialization?`. **You should answer `yes` to this question**.

After the installation is complete, close and reopen your terminal/Miniforge Prompt.

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

#### Create ZIDAS2026 Environment
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

<details>
<summary>Info about the JupyterLite environment</summary>

In this setup, no data is uploaded to the cloud and code is executed in your browser directly. If you modify the notebooks, the modifications will be saved in your browser's local storage. You can download them and also upload new notebooks or data to the environment. To work with a fresh copy, use private/incognito mode or clear the local browser storage.

This is a very convenient way to immediately get started with the notebooks. However, please note that JupyterLite is a limited environment and does not support all features of a full Python installation. For example, you cannot use napari in JupyterLite, therefore the napari notebook is not available in this version. JupyterLite also cannot read TIFF files that require `imagecodecs`, such as compressed TIFFs; the provided tutorial TIFFs are uncompressed and compatible.

</details>

## To cite
If you use the exercise notebooks from this tutorial, please acknowledge it as follows:

Uhlmann, V., Albert, M., Buchholz, T.-O., Fuster-Barceló, C., and Witz, G.  (2026). Image Quantification 101 Tutorial. github.com/uhlmanngroup/imagequantification101

## Further resources
* Miura, K. & Sladoje, N. (2020). Bioimage Data Analysis Workflows. doi.org/10.1007/978-3-030-22386-1
* Bankhead, P. (2022). Introduction to Bioimage Analysis. bioimagebook.github.io
* Holmes, S. & Huber, W. (2018). Modern Statistics for Modern Biology. www.huber.embl.de/msmb

## Acknowledgements
Part of the material from this tutorial was adapted from Paula Balcells' Bachelor Thesis work carried out in the Uhlmann group.
