# Developing Hierarchical Models for Sports Analytics

Decision-making in sports has become increasingly data-driven with GPS, cameras, and other sensors providing streams of information at high spatial and temporal resolution. While machine learning is a popular approach for turning these data streams into actionable information, Bayesian statistical methods offer a robust alternative. They allow for the combining of multiple data sources, a natural means for imputing missing data, as well as full accounting for various system uncertainties.

In particular, hierarchical models provide a means for integrating information at multiple scales and adjusting for biases associated with small sample sizes. I will demonstrate a Bayesian workflow for model development using PyMC version 5, from data preparation through to the summarization of estimates and predictions, using baseball data.

[Recording of tutorial (YouTube)](https://www.youtube.com/watch?app=desktop&v=Fa64ApS0qig)

## Setup

This tutorial assumes that you have [Anaconda](https://www.anaconda.com/distribution/#download-section) (Python 3.11 version) or [Mambaforge](https://github.com/conda-forge/miniforge#mambaforge) (preferred) setup and installed on your system.

The next step is to clone or download the tutorial materials in this repository. If you are familiar with Git, run the clone command:

    git clone https://github.com/fonnesbeck/hierarchical_models_sports_analytics.git
    
otherwise you can [download a zip file](https://github.com/fonnesbeck/hierarchical_models_sports_analytics/archive/master.zip) of its contents, and unzip it on your computer.

In either case, you should now have a directory called `hierarchical_models_sports_analytics` in your current working directory.

    cd hierarchical_models_sports_analytics

The repository for this tutorial contains a file called `environment.yml` that includes a list of all the packages used for the tutorial. If you run:

    conda env create
    
from the main tutorial directory, it will create the environment (called `pymc_sports_analytics`) for you and install all of the packages listed. This environment can be enabled using:

    conda activate pymc_sports_analytics
    
Then, I recommend using JupyterLab (or your favorite Jupyter-supporting editor) to access the materials:

    jupyter lab