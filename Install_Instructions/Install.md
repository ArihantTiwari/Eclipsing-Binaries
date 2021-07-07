# Installations 

# For Windows

If you are using a Windows machine, first check out the setup instructions [here](Install_Instructions/Windows_Install.md). In these instructions, you will be setting up Windows Subsystem for Linux (WSL). 

The Windows Subsystem for Linux lets developers run a GNU/Linux environment -- including most command-line tools, utilities, and applications -- directly on Windows, unmodified, without the overhead of a traditional virtual machine or dualboot setup. WSL is faster and highy efficient than using VM or Dual Boot. To read about this more, you can visit this page: https://docs.microsoft.com/en-us/windows/wsl/about

Once you've followed those instructions, come back and continue here with Linux instructions.

# For Linux
Some commands to run before we start with other package installation:

    sudo apt-get update && sudo apt-get -y upgrade
    sudo apt-get install python3-pip
    sudo apt-get install gcc g++

Additionally, in order to build the C-sources, make sure you have Python.h headers for the correct version of python3, by installing python3-dev via your package manager.
 
  For Debian based linux distribution:
    
    sudo apt-get install python3-dev
    
  For Fedora based linus distribution:
    
    yum install python3-devel 

## Git

For Debian

    sudo apt-get install git

For Arch-Linux

    pacman -S git
    
For other Linux distributions, check out here: https://git-scm.com/download/linux

---

#### Note: For WSL users

Windows and Linux use slightly different line endings. This sometimes causes Linux or Windows to think a file is modified in git when it hasn't been due to different line ending usage. In Linux, run the following line to fix this:

    git config --global core.autocrlf true
---

## Python
We recommend you to use an Anaconda Python installation. 

You can find Anaconda installation instructions here: https://docs.anaconda.com/anaconda/install/linux/

---
**Note**

1. When installing anaconda be sure to follow the prompts and say `yes` to running `conda init` at the last prompt! If you don't your terminal may not be able to recognize the `conda` command. If you miss it you can run it manually with:
```
/[conda install directory]/bin/conda init
```

2. Be sure to restart your terminal after installing conda and running `conda init` to apply the changes! Otherwise you will still be left with the unrecognized `conda` command error. 

---

Now that we have a Python environment for this project, let's install packages that we need. First we want to install `numpy` through conda so that it is compiled with MKL/BLAS so that we can parallelize linear algebra operations. 

    conda install numpy scipy astropy matplotlib
    
To update your python packages in conda, run:

    conda update -y --all

## Conda Environment (Optional)
For all Python users, we strongly recommend that you use conda environments to manage multiple Python versions for multiple projects, especially if you already have python installed for other projects. This prevents projects having conflicting dependencies as each project can have its own Python. Let's create an environment that uses Python 3.

    conda create -n ksp python=3.6

Then, any time you want to use this version of Python from the command line, run the following line of code to set Python to point to this version:

    conda activate ksp

 To verify your installation, run the following line, which will list the path to your python installation. The path should include miniconda/anaconda and ksp:

    which python

Now that we have a Python environment for this project, let's install packages that we need. First we want to install `numpy` through conda so that it is compiled with MKL/BLAS so that we can parallelize linear algebra operations. 

    conda install numpy scipy astropy matplotlib
    
To update your python packages in conda, run:

    conda update -y --all

## Jupyter Notebook

We will be using Interactive Python Notebooks (ipynb) for the majority of our project. You can use Jupyter notebook to run ipynb notebooks. You can also use _Spyder_ or _VSCode_ for this purpose but I have felt that Jupyter Notebooks are more intutive.

Jupyter Notebooks are automatically installed on Anaconda by default. 

To run the notebook in conda (remember to activate ksp environment before running jupyter):
    
    jupyter-notebook

Additionally, you can install some set of extensions for your jupyter notebook to have more functionality and to improve your coding experience. To install jupyter nbextensions, find the instructions here: https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html

## PHOEBE

<img align="left" src="http://phoebe-project.org/logos/logo_release_23.svg" width="120">

This is the main package we are going to use throughout our project. [PHOEBE](http://phoebe-project.org/) stands for PHysics Of Eclipsing BinariEs. It's a python based package with in-built functionalities to model and fit Eclipsing Binaries. PHOEBE is written by an international team of professional astronomers, and is completely open-source, under a GPL v3 License.

Installing PHOEBE from PIP is probably the easiest. Since the build process requires numpy, we'll make sure that's installed first. To install the latest version of PHOEBE:

    pip3 install numpy phoebe
To update a previous installation to the latest release:

    pip3 install -U phoebe
And to uninstall:

    pip3 uninstall phoebe
If pip gives any problems automatically installing dependencies, install them manually first:

    pip3 install numpy scipy matplotlib astropy
Please check the version of PHOEBE you have installed to make sure you are using the corresponding version of the documentation. You can check the version once PHOEBE is installed via:

    python3 -c "import phoebe; print(phoebe.__version__)"
