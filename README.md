# cheminfo_tutorial_20241028

## cheminfomratics handson @ CBI2024年大会

## Breaf introduction

 This is the material for cheminformatics hands-on session at CBI2024

## Participants requirements

- Basic skill of python programming
- Basic knowledge of cheminfomratics
- Unfortunately it's difficult to support Windows os. The code will be tested on Linux, Mac OS but not Windows(inculdes WSL). 

## Prerequreiment

- Please install anaconda
- Please install REINVENT ver4
- Please install Autodock Vina
- Plaese install Maize-dev
- I added an example for making environment

### Install REINVENT4

[reinvent4](https://github.com/MolecularAI/REINVENT4)

- Example code (Ubuntu)

```bash
$ gh repo clone MolecularAI/REINVENT4
$ cd REINVENT4
$ mamba create --name reinvent4 python=3.10
$ mamba activate reinvent4
$ pip install torch==2.2.1 torchvision==0.17.1 torchaudio==2.2.1 --index-url https://download.pytorch.org/whl/rocm5.7
$ pip install --no-deps .
```

### Install Autodocl Vina

- Example code (Ubuntu)

```bash
$ wget https://github.com/ccsb-scripps/AutoDock-Vina/releases/download/v1.2.5/vina_split_1.2.5_linux_x86_64
$ sudo mkdir -p /opt/vina/bin/
$ sudo mv vina_split_1.2.5_linux_x86_64 /opt/vina/bin
$ sudo ln -s /opt/vina/bin/vina_split_1.2.5_linux_x86_64 /opt/vina/bin/vina
$ export PATH=/opt/vina/bin/:$PATH
```

### Install Maize-contrib

- Example code (Ubuntu)

```bash
$ gh repo clone MolecularAI/maize-contrib
$ cd maize-contrib
$ mamba env create -f env-users.yml
$ mamba activate maize
$ pip install --no-deps ./
$ mamba install -c conda-forge pymol-open-source
```


## Author

- Taka
