# Task 1: R package structure and documentation
- [ ] Setup the repository like a proper R package.
- [ ] Extract fit_cause_model and abs_risk_from_cschf as separate
      functions and document them
- [ ] Look through fixme's and hacks and make a plan for fixing them.
- [ ] Write a sandbox script file illustration functionality of the
      package. This should contain at least Cox- and random
      forest-based CHF learners.
- [ ] Incorporate an approximate grid argument which can be used to
      approximate the CHFs and risk predictions based on disretized
      integral. Should also be possible to not use an approximation,
      when the supplied CHF learners a piecewise constant, so that the
      integrals just becomes sums.
	  
# Task 2: testing
- [ ] Write some test for testing expected behaviour. In particular,
      test that standard predictions from a Cox model are equal to
      using the predictCHF and jossl functionality, when other CHF
      function are just zero functions.
- [ ] Test settings with and without censoring

# Task 3: predictCHF method
- [ ] Document existing predictCHF methods and develop or document how
      to construct learners. Make them into proper objects that store
      information about whether the cumulative hazard is continuous or
      piecewise constant. In the later case, it should store the jump
      times of the hazard. In the former case, it should store a
      default suggestion for approximation grid.
- [ ] Implement a CHF predict method and learner for Poisson
      regression. Note that this has a continuous cumulative hazard
      function, so now we can only approximate the integral used for
      risk prediction calculation.
- [ ] Test the jossl functionality using the Poisson regression with
      different approximation grids used, and a Cox learner as learner
      of the competing CHF.
- [ ] Suggest other relevant hazard learner for which to implement a
      predictCHF method (for this, you might need internet access, so
      can ask for permission).
	  
# Task 4: IPCW based super learning
- [ ] Make it an option for the jossl ensemble learner to instead
      assume completely independent censoring and use inverse
      probability of censoring weights estimated with the (reverse)
      Kaplan-Meier estimator. See the riskRegression package for how
      this can be implemented.

# Pending task
Pending, no not attempt to solve below yet, these are just here for
notes

## Reweighting jossl based on IPCW
Use level-1 data and jossl as is to estimate the outcome CHFs and the
CHF of censoring. Then, with the same level-1 data split, estimate
IPCW weights using the estimated censoring CHF. Then construct
ensemble learner for the event prediction(s) using the estimated
IPCWs.

## Convex combinations of learner
Expand the jossl setup to be able to do a proper convex combination of
learner instead of just a simple super learner. Now we construct
separate convex combinations the CHFs for each cause and
censoring. Make a plan for efficient implementation of this and
investigate if the objective function could or could not be convex.

# Blocked
<!-- Codex: record permission or environment failures here, then continue. -->

# Progress log
<!-- Codex: append completed work here. -->
