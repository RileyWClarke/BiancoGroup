# Riley Clarke - Week of 06/16/2019

## 1. 

### 1.1 Papers Read

\<https://arxiv.org/pdf/1008.4686.pdf\> : Data analysis recipes: Fitting a model to data. (David Hogg, Jo Bovy, & Dusting Lang) A summary of linear fitting techniques with an emphasis on the inappropriateness of standard least-squares fitting on data with small uncertainties along a single dimension. Covers the fundamental linear algebra formulation for linear fitting, Bayesian framework for marginalizing and fitting parameters, methods for pruning outliers such as bootstrapping and jackknifing, how to handle non-Gaussian uncertainties, goodness-of-fit metrics, and fitting data with large intrinsic scatter. 

.
.
.
### 1.2 Code Written

BiancoSummer2019.ipynb : Added astroML scatter_contour to K2 H-R diagram. https://github.com/RileyWClarke/BiancoGroupSummer2019/blob/master/BiancoSummer2019.ipynb

LinearFittingExercises.ipynb : Completed Chapter 1 exersizes from Hogg et al. 2010, started work on Chapter 3 exercises. https://github.com/RileyWClarke/BiancoGroupSummer2019/blob/master/LinearFittingExercises.ipynb 

.
.
.
## 2. Figures

![](Figures/k2scatter_contour.pdf?raw=true)

Figure 1 is an H-R diagram of ~300000 stars in the K2 target data obtained from the NASA Exoplanet Archive API. Past a density threshold of 50 points per bin, contours are added to show detail in the high-density regions along the main sequence. 
.
.
.
## 3 Results 

With some help, was able to figure out what was going wrong with using astroML.plotting.scatter_contour to add density contours to the K2 H-R diagram in BiancoSummer2019.ipynb. 

Added a new iPython notebook for completing the end-of-chapter exercises in the linear fitting paper mentioned in Part 1. Completed Exercises 1,2, & 3 from Chapter 1 and started working on the Chapter 3 problems. (Chapter 2 problems don't use the example data; may come back to these.) For Problem 6, I'm using a well-known MCMC library called emcee to do the parameter sampling to obtain the posterior distribution, but having some trouble with the given mixing function returning lots of NaNs.
