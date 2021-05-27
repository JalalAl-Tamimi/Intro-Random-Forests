# Introduction to Random Forests

## Content

This repo contains details of the material used in the workshop **Introduction to Random Forests** delivered to the group: *[Sounds of Language and Speech: Aarhus University's phonetics and phonology (and more) research group](https://soundsoflanguageandspeech.wordpress.com/)*, on 16th June 2021.

In this workshop, we start by introducing very briefly predictive modelling as a classification tool. We (re-)introduce Generalised Linear Models (GLM) as a classification tool. We then present links between GLM and Signal Detection Theory and introduce the notions of accuracy, error, sensitivity, specificity, Area Under the Curve, and dprime. 

We will discuss issues with GLM on correlated data and introduce Decision trees as a possible solution. We will grow our first tree using the Conditional-Inference Trees framework. We use real data from my current research on the *phonetic basis of the guttural natural class in Levantine Arabic* using acoustic predictors of formant bark-differences, and voice quality as obtained from [VoiceSauce](http://www.phonetics.ucla.edu/voicesauce/). We look at how to interpret the tree based on one predictor, before using multiple predictors to evaluate differences between groups. We report on accuracy, sensitivity, specificity, and AUC for each tree. We will try to mimic how Random Forests work based on decision trees, before introducing Random Forests. 

For Random Forests, we will use two frameorks:

1. RF as grown via permutation tests using Conditional-Inference Trees as implemented in the package [party](https://cran.r-project.org/web/packages/party/vignettes/party.pdf) 
2. RF as grow via permutation tests as implemented in the package [ranger](https://cran.r-project.org/web/packages/ranger/ranger.pdf)

We use specific settings in ranger to mimic the unbiased selection process implemented in the package party.

At the end, we introduce the [tidymodels](https://www.tidymodels.org/) and briefly discuss their philosophy. We use ranger as an engine and showcase the strength of tidymodels to facilitate the use of machine learning. 

## To prepare for the workshop, participants will need to 

1. Have knowledge of how to use R, and of the [tidyverse](https://www.tidyverse.org/). We will mostly use RMarkdown to run the code, with an opportunity to practice the code on their own. 
2. Read this paper to familiarise themselves with predictive modelling and the acoustic correlates used: *Al-Tamimi, J. (2017). Revisiting acoustic correlates of pharyngealization in Jordanian and Moroccan Arabic: Implications for formal representations. Laboratory Phonology: Journal of the Association for Laboratory Phonology, 8(1), 28. DOI: [https://doi.org/10.5334/labphon.19](https://doi.org/10.5334/labphon.19)*.
3. Some additional acoustic measures are obtained from [VoiceSauce](http://www.phonetics.ucla.edu/voicesauce/), it would be great if you familiarised yourselves with what the measures reflect. 
4. Install the following packages ahead of the meeting, by running the following code:


```{r}
requiredPackages = c('tidyverse', 'broom', 'knitr', 'corrplot', 'psycho', 
'PresenceAbsence', 'party', 'ranger', 'tidymodels', 'pROC', 'varImp', 
'lattice', 'vip', 'doFuture', 'doRNG', 'parallelly')
for(p in requiredPackages){
  if(!require(p,character.only = TRUE)) install.packages(p)
  library(p,character.only = TRUE)
}
```

Additional material will be added closer to the time.

