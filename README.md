# multivariate_sMRI_analyses

## Study Information

### Title

Neural Characterization of Cross-modality and Cross-linguistic Statistical Learning in Adults

### Authors

Jennifer Legault, Julie Schneider, Brady Robinson, Anqi Hu, and Zhenghan Qi

### Description

#### Impact Statement for general audience

Statistical Learning (SL) reflects the ability to parse patterns and information from the environment.  It is an essential skill for various components of language learning, such as learning about which sounds are important for a target language and learning word boundaries.  However, little is known about how the brain processes this SL information, since there are large variations in behavior and brain structure across individuals.  This study aims to identify the contributions of neural network regions of interest that are tuned to language processing and assess relationships between brain structure in these regions and individual SL performance.  In particular, we are interested in predicting effective SL task performance using neural measures of language processing.  This will help us identify which language-based regions are also important for SL within and between individuals, and whether these relationships differ based on modality or linguistic content of SL tasks. 

### Hypotheses

Overarching goal: Examine how we can predict/model effective SL task performance using neural measures of language processing and multiple demand processing

#### Research Question 1: Which neural language processing characteristics predict various SL tasks?
Follow up RQ: Address consistency and sensitivity of GM vs fMRI data 

#### RQ 2: Which neural multiple demands characteristics predict various SL tasks?
As a control task to examine/determine specificity of relationship between language-related regions and SL tasks.
 
####  RQ 1 Hypotheses:
1. Both GM and fMRI data will show that MRI data correlate with linguistic but not non-linguistic SL
⋅⋅* This would be indicative that 1) neural processing of SL tasks are domain - specific and 2) both GM and fMRI data are consistent and sensitive to SL domain-specific differences
2. Control task: Should have no group differences (or sig cor) between beta weights or GMV and flanker task

#### RQ 2 Hypotheses
1. Any SL tasks may show some correlation with GMV in MD network, however there should not be group differences between linguistic vs non-linguistic SL tasks


## Design Plan

### Analyses to run:
1. Take individual beta weights from intact > degraded and run correlations with various behavioral SL tasks.
2. Take individual GMV/CT from intact > degraded ROIs and run correlations with various behavioral SL tasks
3. Control task: Take individual beta weights and GMV/CT from intact > degraded and run correlations with flanker executive function task
4. Control ROI: select an ROI from the multiple demand (MD) network and take individual beta weights and GMV/CT and run correlations with SL tasks
5. See if adding in GMV from MD network increases confidence/fit/accuracy of model

### Statistical methodologies to look into using

Using multivariate predictive modeling to predict SL performance based off sMRI GM measures and fMRI beta weights, following methodology proposed by Shen et al. (2017).  See also  https://github.com/swglab/CPM_CONN, with emphasis on CPM_internal_permute.m script.  
1. For sMRI measures, inputs to model should be partial correlation values for GM values and SL tasks, controling for intracranial volume (eTIV)
2. For fMRI measures, inputs to model should be correlation values for beta weights and SL tasks
* All behavioral and neural measures should be mean-centered when running the prediction model using leave-one-subject-out cross validation


Keep in mind that "it is important that no information is shared between the training set and the testing data. One common mistake occurs when some normalization is applied to all data before the cross-validation loop. Such overall normalization could contaminate the testing set with information from the training set, erroneously increasing prediction performance. Normalization should always be performed within the training set, and any parameters used (e.g., mean and standard deviation for z-scoring) should be saved to apply to variables in the test set" (Shen et al., 2017).

