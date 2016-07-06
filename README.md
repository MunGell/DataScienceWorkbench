# Data Science Workbench

This repository contains a simple Vagrant box based on Ubuntu 14.04.4 LTS.
It's Ansible provision playbook installs Jupyter, Python 3 kernel and all basic scientific libraries.

## Getting Started

1. Clone/Download the repository
2. Rename file `settings.yml.example` to `settings.yml`
3. Edit any settings that you wish in `settings.yml`
4. Boot up the machine with `vagrant up`
5. Access your notebook using [http://localhost:8888](http://localhost:8888) or hostname:port of your choice

## Jupyter

Latest Jupyter (IPython) is installed through `pip` using Python 3.

## Python kernel

Uses Python 3.
Following `pip` packages are installed:

  - numpy
  - scipy
  - pandas
  - matplotlib
  - scikit-learn
  - networkx


## Roadmap

Finalise R kernel installation that is now blocked by a bug in `devtools` R package.
