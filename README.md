# multivariate_sMRI_analyses

# Blast localizer documentation

## Study Information

### Title

Neural Characterization of Cross-modality and Cross-linguistic Statistical Learning in Adults

### Authors

Jennifer Legault, Julie Schneider, Anqi Hu, and Zhenghan Qi

### Description

#### Impact Statement for general audience

Statistical Learning (SL) reflects the ability to parse patterns and information from the environment.  It is an essential skill for various components of language learning, such as learning about which sounds are important for a target language and learning word boundaries.  However, little is known about how the brain processes this SL information, since there are large variations in behavior and brain structure across individuals.  This study aims to identify the contributions of neural network regions of interest that are tuned to language processing and assess relationships between brain structure in these regions and individual SL performance.  In particular, we are interested in predicting effective SL task performance using neural measures of language processing.  This will help us identify which language-based regions are also important for SL within and between individuals. 

#### Overarching aim of subject-specific functional localizer

To identify subject-specific ROIs tuned to language processing and assess relationships between ROI measures, language processing, and various behavioral tasks.

#### Advantages of subject-specific functional localizer

This approach provides more sensitivity to language processing, greater specificity for language (over other non-linguistic tasks such as working memory), greater reliability of results due to using shared paradigm.

### Hypotheses

Overarching goal: Examine how we can predict/model effective SL task performance using neural measures of language processing and multiple demand processing

#### Research Question 1: Which neural language processing characteristics predict various SL tasks?
Follow up RQ: Address consistency and sensitivity of GM vs fMRI data 

#### RQ 2: Which neural multiple demands characteristics predict various SL tasks?
 
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

K-fold cross-validation (with k = 5)
1. Shuffle the dataset randomly.
2. Split the dataset into k groups
3. For each unique group:
* Take the group as a hold out or test data set
* Take the remaining groups as a training data set
* Fit a model on the training set and evaluate it on the test set
* Retain the evaluation score and discard the model
4. Summarize the skill of the model using the sample of model evaluation scores

Importantly, each observation in the data sample is assigned to an individual group and stays in that group for the duration of the procedure. This means that each sample is given the opportunity to be used in the hold out set 1 time and used to train the model k-1 times.

