# Riley Clarke - Week of 06/24/2019

## 1. 

### 1.1 Papers Read

\<https://iopscience.iop.org/article/10.3847/1538-4357/aab8fe#apjaab8fet2\> : K2 Ultracool Dwarfs Survey III: White Light Flares are Ubiquitous in M6-L0 Dwarfs (Paudel et al. 2018) This paper is a report on 10 flaring ultracool dwarfs (UCDs) using the Kepler/K2 short-cadence data. In total, 283 flares were identified in an energy range of 10^29 - 10^33.5 erg. One motivation for studying flares on these UCDs is to understand how magnetic activity evolves with age and spectral type in the ultracool regime. Unlike most stars, UCDs do not display strong correlation between rotation and common indicators of activity like x-rays and H-alpha. Additionally, the discovery of the TRAPPIST-1 system (an M8 dwarf) showed that cool dwarfs can host planetary systems within their habitable zone, but understanding the magnetic activity of the host star is crucial to evaluating the habitability of any nearby planets, as UV radiation from flares can significantly impact the atmospheric chemistry of a nearby planet.

The authors perform artificial flare injection into the photometry to determine the lowest flare energy detectable by their algorithm, a modified version of the "appaloosa" package (Davenport et al. 2016)

The authors create flare frequency diagrams (FFDs) and fit broken power law lines to the data. A power-law slope < 1 means that the high-energy flares contribute most to the total flare energy, whereas a slope > 1 implies the low-energy flares contribute most to the total flare energy. The authors use the maximum-likelihood method described in Hogg et al. 2010 and the "emcee" MCMC fitting package (Foreman-Mackey et al. 2013) to fit the FFD parameters.

Figure 10 of the paper shows the FFD fits for spectral types M4 through L0+L1. The later spectral types display shallower power law slopes, with 0.43 for the L0+L1 compared to 0.84 for M4. This indicates that surprisingly, the more of the flare energy of the latest UCDs is produced by the highest-energy flares, and indeed, the second-largest flare in the survey (logE ~ 33.95 erg) was on a young (130 Myr) brown dwarf. The presence of super flares on the coolest UCDs suggests that flares are a universal phenomenon in solar-type stars.
.
.
### 1.2 Code Written

BiancoGroup2019.ipynb: Read in Table 3 data from Paudel et al. 2018 using pandas.read_csv() again. Added histograms of flare energy for each target.

LinearFittingExercises.ipynb: Tweaking priors seems to have solved issues with log_likelihood returning too few points. Corner plot shows that the MCMC is actually producing proper posteriors now. Still need to sample MAP fit parameters from results and plot over data.

.
.
.
## 2. Figures

![](Figures/flar_hists.png?raw=true)

Flare energy histograms of each target in Paudel et al. 2018

![](Figures/prob6_corner.png?raw=true)

Corner plot of MCMC results for Problem 6 of Hogg et al. 2010
.
.
.
## 3 Results 

Applied techniques for reading in data (pandas.read_csv()) to Table 3 in Paudel et al. 2018. Created histograms of log flare energy (ergs). Next step is using this data to make my own flare frequency distributions (FFDs) of the ten targets from the paper.

Finally seeing some success on the Emcee front! Turns out choosing reasonable priors is VERY important, and sometimes they need to be tweaked a bit. The issue was that I was initiating the MCMC walkers at an m value outside the specified prior. Unsurprisingly, this resulted in very few valid values being returned by the log_likelihood function while the walkers were roaming about in parts of parameter space excluded by the priors I had set. Next step is plotting the posterior fits against the data and selecting the MAP value s as the true fit.