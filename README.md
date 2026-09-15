# Trial-by-Trial Updating of Prior Beliefs in the IBL Decision-Making Task

## Overview

This project investigates how prior information and recent trial history are reflected in neural activity during the International Brain Laboratory (IBL) decision-making task.

The analysis focuses on population-level neural decoding across broad brain-region groups.

## Current Analysis

The current analysis includes:

1. Baseline current-choice decoding
2. History-dependent choice decoding
3. Time-resolved choice decoding
4. Temporal window × history analysis

The subjective-prior modeling and prior-decoding analyses are not yet included and will be developed in subsequent stages.

## Dataset

The project uses the IBL Brain-Wide Map dataset accessed through the NeuroConnect analysis environment.

## Brain-Region Groups

The exploratory analysis currently uses four broad region groups:

* Sensory
* Motor
* Memory
* Integrative

These groups are used for exploratory regional comparison and do not represent homogeneous functional categories.

## Methods

Current analyses use:

* Population neural activity extracted around stimulus onset
* Logistic regression
* L2 regularization
* Standardization within the cross-validation pipeline
* Stratified cross-validation
* Time-resolved population decoding

## Scientific Scope

Pre-stimulus choice decoding is not interpreted as direct evidence of prior-belief representation. Pre-stimulus activity may contain information related to previous choices, feedback history, block state, latent task state, motor preparation, and other factors.

The primary scientific objective is to develop a behaviorally grounded estimate of subjective prior beliefs and subsequently test whether these beliefs can be decoded from neural population activity.

## Status

**Current stage:** Exploratory decoding analysis

Subjective prior modeling and neural prior decoding are ongoing.
