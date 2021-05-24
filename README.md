# Introduction to Random Forests

This repo contains details of the material used in the workshop **Introduction to Random Forests** delivered to the group: *[Sounds of Language and Speech: Aarhus University's phonetics and phonology (and more) research group](https://soundsoflanguageandspeech.wordpress.com/)*, on 16th June 2021.

In this workshop, we start by introducing very briefly predictive modelling as a classification tool. We (re-)introduce Generalised Linear Models (GLM) as a classification tool. We present links between GLM and Signal Detection Theory and introduce the notions of accuracy, error, sensitivity, specificity, Area Under the Curve, and dprime. 

We then introduce Decision trees and use the Conditional-Inference Trees to grow our first tree. We use real data from my current research on the *phonetic basis of the guttural natural class in Levantine Arabic* using acoustic predictors of formant bark-differences, and voice quality as obtained from [VoiceSauce](http://www.phonetics.ucla.edu/voicesauce/). We look at how to interpret the tree based on one predictor, before using multiple predictors to evaluate differences between groups. We report on accuracy, sensitivity, specificity and AUC for each tree. 

We then move to Random Forests and use two frameworks: 
1. RF as grown via permutation tests using Conditional-Inference Trees as implemented in the package [`party`](https://cran.r-project.org/web/packages/party/vignettes/party.pdf) 
2. RF as grow via permutation tests as implemented in the package [`ranger`](https://cran.r-project.org/web/packages/ranger/ranger.pdf)

We use specific settings in `ranger` to mimic the unbiased selection process implemented in the package `party`.

At the end, we introduce the [`tidymodels`](https://www.tidymodels.org/) and discuss briefly their philosophy. We use `ranger` as an engine and showcase the strength of `tidymodels` as a way to facilitate and homogonies the use of machine learning. 

To prepare for the workshop, participants are asked to read this paper to familiarise themselves with predictive modelling and the acoustic correlates used: *Al-Tamimi, J. (2017). Revisiting acoustic correlates of pharyngealization in Jordanian and Moroccan Arabic: Implications for formal representations. Laboratory Phonology: Journal of the Association for Laboratory Phonology, 8(1), 28. DOI: [http://doi.org/10.5334/labphon.19](http://doi.org/10.5334/labphon.19)*

Make sure to install the following packages ahead of the meeting, by running the following code:

`requiredPackages = c('tidyverse', 'broom', 'knitr', 'corrplot', 'psycho', 'PresenceAbsence', 'party', 'ranger', 'tidymodels', 'pROC', 'varImp', 'lattice', 'vip', 'doFuture', 'doRNG', 'parallelly', 'parallel')
for(p in requiredPackages){
  if(!require(p,character.only = TRUE)) install.packages(p)
  library(p,character.only = TRUE)
}
`

Additional material will be added closer to the time

