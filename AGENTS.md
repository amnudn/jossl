Should run codex with

    codex --sandbox workspace-write --ask-for-approval on-request -c approvals_reviewer=auto_review 

# R package
This repository contain draft code for an R package implementing the
super learner JoSSL for right-censored data. The approach is
documented in the article 

    ./jossl-article.pdf

# General JoSSL structure
The central idea is that we build cumulative hazard learners and
combine them for estimating the observed data distribution. We use
this combination for constructing an ensemble/super learner of the
probability of the observed, potentially censored event time, where
censoring is considered a state of its own. From this, we can extract
relevant cumulative hazard function(s) and construct a risk prediction
model.

The main workhorses are the methods for constructing and predicting
cumulative hazard functions and the function for combining estimated
cumulative hazard functions into predictions for both observed event
probabilities and event probabilities for the uncensored distribution
of interest.
