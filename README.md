<!--
-*- coding: utf-8 -*-

 Author: Jantine Broek <jantine@mysine.io>
 License: MIT
-->

# Biosignal Simulations

## Table of Contents
1. [General Info](#general-info)
2. [Model and Data](#model-and-data)
3. [Build and Run](#build-and-run)
4. [License](#license)

<a name="general-info"></a>
## General Info

This repository contains implementations of various simulation techniques for biological signals. The goal is to generate synthetic biosignals that accurately model and capture the dynamics of physiological processes using stochastic methods, Markov chains, and Monte Carlo simulations.

### Repository Structure

```
biosignal_simulations/
├── notebooks/                     # Jupyter notebooks
│   ├── blood_signal_simulation.ipynb     # Models for blood-related signals
│   ├── markov_chain.ipynb               # Basic Markov chain implementations
│   ├── stochastic_markov_neuro.ipynb    # Stochastic Markov chains for neural data
│   └── monte_carlo.ipynb                # Monte Carlo simulation techniques
├── results/                       # Output from simulations
│   ├── figures/                   # Generated plots and visualisations
│   └── data/                      # Generated synthetic data
├── configs/                       # Configuration files
│   ├── params.yaml                # Simulation parameters, etc.
│   └── data_paths.yaml            # Paths to validation data
├── scripts/                       # Command-line scripts
├── .pre-commit-config.yaml        # Pre-commit hooks configuration
├── requirements.txt               # Project dependencies
├── setup.py                       # Make the project installable
├── README.md                      # Project documentation
└── .gitignore                     # Include patterns to ignore large data files
```

<a name="model-and-data"></a>
## Model and Data

This repository includes implementations of:

1. **Blood Signal Simulations**:
   - Pulse wave simulations
   - Blood pressure waveforms
   - Flow dynamics and turbulence models

2. **Markov Chain Models**:
   - Discrete state transitions
   - Continuous-time Markov chains
   - Hidden Markov models for biosignal patterns

3. **Stochastic Markov Models for Neuroscience**:
   - Neural spike train simulations
   - Ion channel kinetics
   - Network activity with stochastic components

4. **Monte Carlo Simulations**:
   - Parameter estimation in physiological models
   - Uncertainty quantification
   - Sampling from complex biological distributions

The simulations are implemented in Jupyter notebooks with interactive components for parameter adjustments and visualisation of results.

<a name="build-and-run"></a>
## Build and Run

### How to Build

This repository uses Git Large File Storage (Git LFS) to handle large simulation output files. To clone and use this repository:

1. Install Git LFS if you haven't already:
   ```bash
   # For Ubuntu/Debian
   apt-get install git-lfs

   # For macOS with Homebrew
   brew install git-lfs

   # For Windows with Chocolatey
   choco install git-lfs
   ```

2. Enable Git LFS:
   ```bash
   git lfs install
   ```

3. Ensure you have Python 3.8 or higher installed.
4. Clone the repository:
   ```bash
    git clone https://github.com/MYSINELTD/biosignal_simulations.git
    cd MYSINELTD/biosignal_simulations
   ```

5. Pull the LFS files:
   ```bash
   git lfs pull
   ```

6. Create a conda environment:

    ```bash
    conda create -n biosim python=3.11
    conda activate biosim
    ```

7. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

### Install the Packages

1. If you need to access related data repositories, clone them in the same parent directory:

   ```bash
   mkdir -p ~/Projects/MYSINELTD
   cd ~/Projects/MYSINELTD
   git clone https://github.com/MYSINELTD/biosignal_simulations.git
   # Clone any data repositories if needed
   ```

2. Add this to your .bashrc or .zshrc file for persistence:

   ```bash
   export BIOSIM_DATA_DIR=~/Projects/MYSINELTD/data/raw
   ```

3. Install the package locally in your conda environment:

    ```bash
    pip install -e .
    ```

### How to Run

This repository uses Pre-Commit to maintain PEP8 standards. To use Pre-Commit:

1. Activate your conda environment:

    ```bash
    conda activate biosim
    ```

2. Install pre-commit hooks:

    ```bash
    pip install pre-commit
    pre-commit install
    ```

3. Test the Pre-Commit hooks:

    ```bash
    pre-commit run --all-files
    ```

4. Run the Jupyter notebooks:

    ```bash
    jupyter lab
    # or
    jupyter notebook
    ```

5. Available Simulations:
   - **Blood Signal Simulation**: Open `notebooks/blood_signal_simulation.ipynb`
   - **Markov Chain Models**: Open `notebooks/markov_chain.ipynb`
   - **Stochastic Markov Models for Neuroscience**: Open `notebooks/stochastic_markov_neuro.ipynb`
   - **Monte Carlo Simulations**: Open `notebooks/monte_carlo.ipynb`

## License

MIT