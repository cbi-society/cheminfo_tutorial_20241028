# cheminfo_tutorial_20241028

## cheminfomratics handson @ CBI2024年大会

## Breaf introduction

 This is the material for cheminformatics hands-on session at CBI2024

## Participants requirements

- Basic skill of python programming
- Basic knowledge of cheminfomratics
- Unfortunately it's difficult to support Windows os. The code will be tested on Linux, Mac OS but not Windows(inculdes WSL).

## Prerequreiment

- Install anaconda or mambaforge
- Install REINVENT ver4
- Install Autodock Vina
- Install Gypsum-DL
- Install Maize-contrib ver 0.5.5

### Tips

- mamba is a reimplementation of the conda package manager in C++. And it works faster than conda but it maight be cause problem for building process.
- Following examples use conda but you can use mama at your own risk.
- [miniconda](https://docs.anaconda.com/miniconda/)
- [mambaforge](https://github.com/conda-forge/miniforge)

### Install REINVENT4

- I added an example for making environment

[reinvent4](https://github.com/MolecularAI/REINVENT4)

- Example code (Ubuntu24.04)

```bash
$ git clone https://github.com/MolecularAI/REINVENT4.git
$ cd REINVENT4
$ conda create --name reinvent4 python=3.10
$ conda activate reinvent4
$ pip install torch==2.2.1 torchvision==0.17.1 torchaudio==2.2.1 --index-url https://download.pytorch.org/whl/rocm5.7
$ pip install --no-deps .
```

### Install Autodocl Vina

- Example code (Ubuntu24.04)
- The example put vina on /opt/vina but you can put vina any place.

```bash
$ wget https://github.com/ccsb-scripps/AutoDock-Vina/releases/download/v1.2.5/vina_split_1.2.5_linux_x86_64
$ sudo mkdir -p /opt/vina/bin/
$ sudo mv vina_split_1.2.5_linux_x86_64 /opt/vina/bin
$ sudo ln -s /opt/vina/bin/vina_split_1.2.5_linux_x86_64 /opt/vina/bin/vina
$ export PATH=/opt/vina/bin/:$PATH
```

### Install Gypsum-DL

- Example code (Ubuntu24.04)
- if you don't have mpi, remove mpi4py from the following command.

```bash
$ sudo apt info openmpi-bin
$ conda create --name gypsum python=3.10
$ conda activate gypsum
$ conda install -c conda-forge rdkit numpy scipy mpi4py
$ git clone https://github.com/durrantlab/gypsum_dl.git
```

### Install Maize-contrib

- Example code (Ubuntu24.04)

```bash
$ git clone https://github.com/MolecularAI/maize-contrib.git
$ cd maize-contrib
$ conda env create -f env-users.ymlhttps://github.com/DavidAnson/markdownlint/blob/v0.35.0/doc/md014.md
$ conda activate maize
$ pip install --no-deps ./
$ conda install -c conda-forge pymol-open-source
```

- For MacOS user
  - If you got the error *module 'os' has no attribute 'sched_getaffinity'*, please install fork version of maize in your environment.
  - [mishimasyk/maize](https://github.com/Mishima-syk/maize/tree/public)
  - The issue is reporeted to the original [repo](https://github.com/MolecularAI/maize).

### Reference & Link

- [Anaconda](https://github.com/conda-forge/miniforge)
- [REINVENT ver4](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-024-00812-5)
- [Autodock Vina](https://vina.scripps.edu/)
- [Gypsum-DL](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-019-0358-3)
- [Maize-contrib](https://github.com/MolecularAI/maize-contrib)

### Misc

- maize cofiguration file
  - By default Config will look for a configuration file named maize.toml in $XDG_CONFIG_HOME (usually at ~/.config/,) [detail](https://molecularai.github.io/maize/docs/userguide.html)
  - The repo provides example maize.toml for SBDD WF. We will configure it in this handson training ;-)

  ```bash
  $ echo $XDG_CONFIG_HOME
  /home/iwatobipen/.config
  $ cat /home/iwatobipen/.config/maize.toml
  # maize global configuration file example
  # Where to save temporary files and all workflow directories
  scratch = "/tmp"
  ```

- Tested OS
  - [x] Ubuntu24.04
  - [ ] Ubuntu22.04
  - [ ] MacOS M1
  - [ ] MacOS M2
  - [ ] Windows

## Author

- Kazufumi Okawa
- Koichiro Arai
- Natsumi Miyano
- Kazutoshi Takahashi
- Takayuki Serizawa
