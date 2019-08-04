---
marp: true
paginate: true
_paginate: true
---
<!-- class: invert -->
<!-- _class: invert -->

# Causal analysis and extrapolating data to the real world

**Andrew Gelman**
03 August 2019

---

The problem - causal inference and generalization
---


Generalization :

- We do an experiment in location A, and we want to generalize to location B
- Dosing : it is a modelling problem. Need a model for conc. inside the body, so generalizing from one dose to another dose
- Inferring effect of a drug based on known effect of another drug, etc
- Generalization requires some understanding of causality 

---

How to do it
---

"If the problem is hard, embed it in a larger problem and that makes it easier.." .. the "blessing of dimentionality" in stats.

- do the experiment lots of times
- in each experiment vary every relevant variable
- include time etc.
- use predictive model to generalize to new experiment

---

It is immoral to collect real data without simulating fake data and running the experiment on it. stating assumptions and priors, defining expectations.

"partial pooling" ?

terrible priors can give terrible reccommendations 

---

takes 16 times more data to estimate interactions than to estimate main effects with the same confidence interval.

"The freshman fallacy" - just because freshmen think something, it is wrong.

if our sample not representative of the population, we need interactions in the model.

So, basically, 95% confidence is unreasonable. be satisfied with less. handle uncertainty, use bayesian methods.

if you are too sure of everything, either model is too limited or you spent too much time on data collection :D

---

The folk theorem of statistical computing : if you have a problem with your computing, you have a problem with your model.

methods in survey literature to tackle causal inferenece problems. 

---

Take home message
---

embed data/problem in larger framework and that may lead to better and clearer decisions.

basically, don't just do the thing you are doing. include loads of other relevant variable, and do a hierarchical model.

"the multilevel model is most effective when you don't need it"

---

when a bayesian model is slow :

- code it better
- brute force, GPU etc.
- tuning adaptation for hamiltonian MC etc.
- approximate algorithms
- stacking bayesian models
- break up data into different pieces (systematic ? random ?) and put it together in a model
  - and Gelman came up with a way to do this called expectation propagation, but its not implemented in most standard software
