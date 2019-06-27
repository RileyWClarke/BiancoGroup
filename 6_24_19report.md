# Riley Clarke - Week of 06/24/2019

## 1. 

### 1.1 Papers Read

\<https://iopscience.iop.org/article/10.3847/1538-4357/aab8fe#apjaab8fet2\> : K2 Ultracool Dwarfs Survey III: White Light Flares are Ubiquitous in M6-L0 Dwarfs (Paudel et al. 2018) This paper is a report on 10 flaring ultracool dwarfs (UCDs) using the Kepler/K2 short-cadence data. In total, 283 flares were identified in an energy range of $10^{29} - 10^{33.5}$ erg. One motivation for studying flares on these UCDs is to understand how magnetic activity evolves with age and spectral type in the ultracool regime. Unlike most stars, UCDs do not display strong correlation between rotation and common indicators of activity like x-rays and H-alpha. Additionally, the discovery of the TRAPPIST-1 system (an M8 dwarf) showed that cool dwarfs can host planetary systems within their habitable zone, but understanding the magnetic activity of the host star is crucial to evaluating the habitability of any nearby planets, as UV radiation from flares can significantly impact the atmospheric chemistry of a nearby planet.

The authors perform artificial flare injection into the photometry to determine the lowest flare energy detectable by their algorithm, a modified version of the "appaloosa" package (Davenport et al. 2016)

The authors create flare frequency diagrams (FFDs) and fit broken power law lines to the data. The power law is given by $log(\tilde{\nu} = \alpha_0 - \beta logE$, where $\alpha_0$ is the frequency-intercept and $\beta$ is the slope of the fit. A $\beta < 1$ means that the high-energy flares contribute most to the total flare energy, whereas a $\beta > 1$ implies the low-energy flares contribute most to the total flare energy. The authors use the maximum-likelihood method described in Hogg et al. 2010 and the "emcee" MCMC fitting package (Foreman-Mackey et al. 2013) to fit the FFD parameters ($\alpha_0$ & $\beta$)

Figure 10 of the paper shows the FFD fits for spectral types M4 through L0+L1. The later spectral types display shallower power law slopes, with $\beta = 0.43$ for the L0+L1 compared to $\beta = 0.84$ for M4. 
.
.
.
### 1.2 Code Written

LinearFittingExercises.ipynb : Completed Chapter 1 exercises from Hogg et al. 2010, started work on Chapter 3 exercises. https://github.com/RileyWClarke/BiancoGroupSummer2019/blob/master/LinearFittingExercises.ipynb 

.
.
.
## 2. Figures

![](Figures/k2scatter_contour.png?raw=true)

Figure 1 is an H-R diagram of ~300000 stars in the K2 target data obtained from the NASA Exoplanet Archive API. Past a density threshold of 50 points per bin, contours are added to show detail in the high-density regions along the main sequence. 
.
.
.
## 3 Results 

