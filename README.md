# Project 1

# Data Set: 
MIT-BIT Arrythmia Database: Arrythmia is an abnormal heart rhythm. This is a classic dataset that a day of ECG time series measurements for 4,000 patients. (https://www.physionet.org/content/mitdb/1.0.0/)

## Project Overview

This project analyzes electrocardiogram (ECG) data to understand and model cardiac arrhythmias—those moments when your heart rhythm goes a bit off-script. Using one of the most famous datasets in medical data science, we're digging into what makes hearts skip, flutter, and beat irregularly.

## Navigating This Repo

```
├── question1.ipynb          # Data exploration and phenomenon description
├── question2.ipynb          # Non-parametric modeling approaches
├── question5.ipynb          # Critical evaluation and conclusions
├── q384(markov+syntheticdata).ipynb  # Markov models and synthetic data generation
├── project_1_rules.ipynb    # Project requirements and outline
├── extracted_records/       # Processed ECG data
└── mit-bih-arrhythmia-database-1.0.0/  # The original dataset
```

### Background

The data was collected between 1975-1979 by researchers at Boston's Beth Israel Hospital (now Beth Israel Deaconess Medical Center) and MIT. They specifically chose some records to include rare but clinically important arrhythmias that you wouldn't find in a purely random sample. Here are some specific unique characteristics that helped us contextualize and understand the columns and vlaues of our dataset:

- **48 half-hour ECG recordings** from 47 different people
- **360 measurements per second** - that's detailed enough to catch even subtle irregularities
- **Expert-annotated beats** - multiple cardiologists labeled each heartbeat, so we know what we're looking at
- **Mixed population** - about 60% hospital inpatients and 40% outpatients, giving us diverse cardiac profiles

### The Phenomenon: Cardiac Arrhythmias
Arrhythmias are basically your heart's rhythm section getting out of sync. We're focusing on:

- **Premature Ventricular Contractions (PVCs)**: Early beats that start in the wrong part of the heart
- **Atrial Premature Beats**: Similar concept, but starting in the upper chambers
- **Various conduction abnormalities**: When the electrical signals take weird paths through the heart

What makes these interesting from a data perspective? They have:
- **Distinct morphological signatures** (weird shapes in the ECG)
- **Specific timing patterns** (beats coming too early or too late)
- **Clinical significance** (some patterns are harmless, others need attention)

## Our Modeling Approach

We're using **non-parametric models** because heart rhythms don't always follow nice mathematical formulas. Think of it as letting the data speak for itself rather than forcing it into predetermined boxes:

- **Empirical distributions**: Learning what "normal" and "abnormal" actually look like from the data
- **Kernel density estimates**: Smoothing out the patterns to understand the underlying rhythms
- **Markov transition models**: Capturing how the heart moves between different states (normal → PVC → back to normal)
- **Local regression**: Finding patterns without assuming they're the same everywhere

### The Challenges We Faced
- **Data complexity**: ECG signals are messy with lots of noise and individual variation
- **Imbalanced classes**: Normal beats are common, specific arrhythmias are rare
- **Temporal dependencies**: Heartbeats aren't independent—each one influences what comes next
- **Clinical relevance**: Making sure our models actually reflect medically important patterns

## What We're Creating

Depending on which approach works best, we're either:
- **Generating synthetic ECG sequences** that mimic real arrhythmia patterns, or
- **Bootstrapping clinical metrics** like PVC burden or arrhythmia frequency

The goal is to create something that captures the essential character of real cardiac data while being useful for testing algorithms or understanding patterns.





