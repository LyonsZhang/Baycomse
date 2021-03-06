
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%This is the Bayesian Composition Selection package%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%Please refer to our paper%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%Bayesian compositional regression with structured priors for microbiome feature selection%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%by Liangliang Zhang, Yushu Shi, Robert R. Jenq, Kim-Anh Do, Christine B. Peterson%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%All rights reserved%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

This package includes 4 folders: BayesianContrast, BayesianGeneralize, RealDataRelated and GenerateSimData. 

1. 'BayesianContrast' stands for Bayesian compositional regression with contrast transformations. 

Within this folder, 'ContrastCoreFunctions' consists of all the functions that will be called when implementing simulation or real data analysis.
The most important two functions are 'BayesFactor.m' and 'gibbsgamma.m'.
The first one calculates the Bayes factor.
The second one samples from the conditional posterior distribution of gamma with excluding or including one model index at each iteration.

'ContrastRealrun' includes the executive functions for real data analysis. Generated numerical and graphical results will be saved in this folder.
You need to prepare the following input data: OTU table, continous outcome and similarity matrix between OTUs.

'ContrastSimulation' includes the executive functions for different simulation scenarios. Generated numerical and graphical results will be saved in 'results/simulation'.
In each sub-folder of 'ContrastSimulation', there are 3 functions--crosstest51.m, simulate51.m and simulate51stable.m
The first one splits the data into 90% training data and 10% testing data. It calculates prediction error, false positives and false negatives.
The second one runs the variable selection on the data once.
The third one runs sensitivity analysis by changing the sparsity parameter a.

2. 'BayesianGeneralize' stands for Bayesian compositional regression with generalized transformations. 

Within this folder, 'GeneralizeCoreFunctions' consists of all the functions that will be called when implementing simulation or real data analysis.
The most important two functions are 'BayesFactor.m' and 'gibbsgamma.m'.
The first one calculates the Bayes factor.
The second one samples from the conditional posterior distribution of gamma with excluding or including one model index at each iteration.

'GeneralizeRealrun' includes the executive functions for real data analysis. Generated numerical and graphical results will be saved in this folder.
You need to prepare the following input data: OTU table, continous outcome and similarity matrix between OTUs.

'GeneralizeSimulation' includes the executive functions for different simulation scenarios. Generated numerical and graphical results will be saved in 'results/simulation'.
In each sub-folder of 'GeneralizeSimulation', there are 3 functions--crosstest51.m, simulate51.m and simulate51stable.m
The first one splits the data into 90% training data and 10% testing data. It calculates prediction error, false positives and false negatives.
The second one runs the variable selection on the data once.
The third one runs sensitivity analysis by changing the sparsity parameter a.


3. 'RealDataRelated' consists of executive functions that process microbiome data and calculate association matrices based on phylogenetic tree.

These functions are written in R.
'phylodistance.R' calculates the distance and correlation along the phylogenetic tree.
'plotcirculartree.R' plots the phylygenetic tree in a circular manner.
'plotBayesianprediction.R' plots the fitted predictions vs. observations. 
'plotCorPre.R' plots the correlation and precision matrix obtained from microbiome data.


4. 'GenerateSimData' consists of executive functions that generate different simulations scenarios that will be used in 'ContrastSimulation' and 'GeneralizeSimulation'.

The codes are named as follows, for example, datageneration_str1_snr1_n50_p30.m, denotes independent structure with signal noise ratio 1, sample size n=50 and number of variables p=30. 
'CoreFunctions' includes the codes that will be called when implementing data generations. 

