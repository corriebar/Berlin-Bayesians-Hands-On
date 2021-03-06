# Berlin Bayesians Hands On Session


## The data
We're using the [World Happiness Report](http://worldhappiness.report/) from 2018. We made some preprocessing to the data so that it is easier to work with. If you want to see the processing steps, check this [file](Data_Processing.md). The resulting data frame is called [`preprocessed_data.csv`](data/preprocessed_data.csv).

A short exploratory data analysis with a description of important variables can be found [here](EDA.md).



## Install your favorite framework
In case this is your first time trying out some Bayesian analysis frameworks, please make sure to have any frameworks you would like to try installed beforehand! The most popular languages are Stan and PyMC3 where Stan has a wide variety of interfaces to common programming languages

PyMC3:
https://docs.pymc.io/

Stan has interfaces for R, Python, Matlab, Julia, Stata, Mathematica, and Scala. The most commonly used interfaces for Stan are R and Python.
It also has 2 high-level interfaces for R that are very beginner-friendly: rstanarm and brms.

For use in R, consider also the complentary packages shinystan, bayesplot and loo.

https://mc-stan.org/users/interfaces/

If you use PyStan or PyMC3, consider also the package ArviZ. It is a Python package for visualization of Bayesian models
https://arviz-devs.github.io/arviz/

### Prepared PyMC3/ArviZ environment

Provided you have a local Anaconda installation (see [here](https://www.anaconda.com/distribution/) and [here](https://docs.anaconda.com/anaconda/install/)), you can use our prepared PyMC3/ArviZ environment ([YAML-File](berlinbayesians_environment.yml)).

This should come with the most relevant PyMC3-centric Bayesian Data Analysis packages. Simply run the following command

`conda env create -f berlinbayesians_environment.yml`

A short working example of how to implement a linear model in PyMC and visualize it with Arviz can be found [here](https://github.com/ermeel86/ermeel86.github.io/blob/master/meetups/berlinbayesians/PyMC3_ArviZ_Practical_Minimum.ipynb).

## Get started
If you don't know where to start, consider some of these examples:

PyMC3: https://docs.pymc.io/nb_examples/index.html

Stan: https://mc-stan.org/docs/2_18/stan-users-guide/linear-regression.html

PyStan: https://mc-stan.org/users/documentation/case-studies/pystan_workflow.html

RStan: https://mc-stan.org/users/documentation/case-studies/rstan_workflow.html

RStanArm: http://mc-stan.org/rstanarm/articles/continuous.html

brms: http://paul-buerkner.github.io/brms/


