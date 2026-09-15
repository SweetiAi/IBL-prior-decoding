# Trial-by-Trial Updating of Prior Beliefs in the IBL Decision-Making Task

## Overview

This project investigates how prior information and recent trial history are reflected in neural population activity during the International Brain Laboratory (IBL) decision-making task.

The long-term goal is to test whether **subjective prior beliefs** can be decoded from pre-stimulus neural activity and how their representation varies across brain regions and over time.

The current stage focuses on exploratory neural decoding analyses that establish a baseline before introducing explicit behavioral models of subjective prior beliefs.

---

## Research Question

How does trial history shape the neural information available before a decision, and can a behaviorally estimated **subjective prior belief** be decoded from neural population activity?

The analysis is motivated by previous work showing that prior information can be represented across distributed brain regions during decision-making.

Rather than treating the experimentally imposed block prior as a direct measure of an animal's internal belief, this project aims to first estimate trial-by-trial subjective beliefs from behavior and then test their neural decodability.

---

## Dataset

The project uses data from the **International Brain Laboratory (IBL) Brain-Wide Map** dataset, accessed through the NeuroConnect analysis environment.

The IBL decision-making task involves visual stimuli, left/right choices, probabilistic blocks, and trial outcomes.

Relevant behavioral variables include:

* `probabilityLeft`
* `choice`
* `feedbackType`
* `contrastLeft`
* `contrastRight`
* `block`
* `block_trial_number`

Neural activity is analyzed around stimulus onset using population activity extracted from recorded units.

The original IBL/NeuroConnect tutorial is used as the data-access and analysis environment; this repository contains the project-specific analyses developed on top of that workflow.

---

## Current Analysis

The current notebook contains four exploratory analyses:

### 1. Baseline Choice Decoding

Current left/right choice is decoded from population activity during the late pre-stimulus period:

**−0.4 to 0 s relative to stimulus onset**

This provides a baseline for asking whether information relevant to the upcoming choice is present before stimulus presentation.

### 2. History-Dependent Choice Decoding

Current choice decoding is compared between trials following:

* a rewarded trial
* an unrewarded trial

This analysis examines whether recent feedback history is associated with changes in the decodability of current choice.

### 3. Time-Resolved Choice Decoding

Choice decoding is evaluated in 50-ms temporal bins from:

**−0.4 to +0.8 s**

This characterizes the temporal evolution of choice-related information around stimulus onset.

### 4. Temporal Window × History Analysis

Choice decoding is evaluated over time separately following rewarded and unrewarded trials.

This provides a descriptive view of whether the relationship between recent feedback and choice decodability changes across time.

---

## Brain-Region Groups

The current exploratory analysis uses four broad anatomical groups:

| Group           | Regions                                      |
| --------------- | -------------------------------------------- |
| **Sensory**     | VISp, VISl, VISam, VISpm, VISrl, VISa        |
| **Motor**       | MOs, MOp                                     |
| **Memory**      | CA1, CA2, CA3, DG, SUB                       |
| **Integrative** | PL, ILA, ORBpt, ORBvl, ORBm, PFC, ACAd, ACAv |

These groups are used for exploratory regional comparison.

They should not be interpreted as homogeneous functional systems. In particular, the **Integrative** group contains anatomically and functionally heterogeneous regions.

---

## Decoding Approach

The current analyses use:

* Population neural activity
* Pre-stimulus and peri-stimulus temporal windows
* Logistic regression
* L2 regularization
* Standardization within the cross-validation pipeline
* Stratified cross-validation
* Time-resolved decoding
* Comparison across broad anatomical groups

The current decoder is intended as an exploratory baseline rather than a final inferential model.

---

## Important Scientific Considerations

Pre-stimulus choice decoding is **not interpreted as direct evidence of prior-belief representation**.

Neural activity before stimulus onset may contain information related to several factors, including:

* previous choice
* previous feedback
* block state
* objective prior probability
* latent task state
* motor preparation
* ongoing behavioral state
* other trial-history effects

Therefore, decoding current choice alone cannot distinguish among these possible sources of information.

A central aim of the next stage is to explicitly model behavioral history and estimate a trial-by-trial subjective prior.

---

## Planned Analysis

The next stage of the project will introduce **subjective prior modeling**.

The planned workflow is:

1. Establish the objective block prior as a baseline.
2. Build a history-dependent Bayesian model of belief updating.
3. Estimate trial-by-trial subjective prior beliefs from behavior.
4. Test whether subjective prior can be decoded from neural population activity.
5. Compare decoding across brain-region groups.
6. Characterize the temporal dynamics of prior-related information.
7. Evaluate potential confounds and robustness using appropriate cross-validation and control analyses.

The distinction between **objective prior**, **modeled subjective prior**, and **neural representation of prior** will be maintained throughout the analysis.

---

## Repository Structure

```text
IBL-prior-decoding/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── IBL_prior_decoding_analysis.ipynb
│
└── results/
    ├── figures/
    └── tables/
```

The notebook contains the current exploratory analysis.

The `results/` directory contains selected analysis outputs and figures. Raw experimental data are not stored in this repository.

---

## Project Status

**Current stage:** Exploratory neural decoding

### Completed

* IBL dataset exploration
* Baseline choice decoding
* History-dependent choice decoding
* Time-resolved choice decoding
* Temporal window × history analysis
* Initial regional comparisons

### In progress

* Subjective prior modeling
* Trial-by-trial Bayesian belief estimation
* Neural decoding of subjective prior
* Robustness and control analyses

---

## Scientific Scope

The project is designed as a step-by-step investigation rather than a claim that pre-stimulus choice decoding directly reflects prior beliefs.

The central progression is:

**behavioral history → subjective belief model → neural decoding → regional and temporal characterization**

This separation is important for distinguishing what is directly measured from what is inferred by the model.
