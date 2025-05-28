# Cancer Progression Modeling

This repository presents a multi-perspective approach to modeling and classifying cancer cell population dynamics. It combines **deterministic ODE modeling**, **stochastic simulation (Gillespie algorithm)**, and **machine learning (ML)** techniques to better understand the conditions under which cancerous populations go extinct or grow uncontrollably.

### Authors: 
Rebecca Wang: lufanw@uw.edu, Anja Vogt: anjav@uw.edu, Alexis Georgiades: alexisg8@uw.edu

## Repository Structure

## Project Overview

This project was developed as part of an research project in the AMATH Department at the University of Washington (Spring 2025). The goal is to simulate, analyze, and predict cancer progression under varying biological conditions using computational and data-driven methods.

## Dataset Information

**About the Dataset**  
This dataset focuses on one of the most prevalent forms of childhood cancer: **Acute Lymphoblastic Leukemia (ALL)**. It consists of **15,135 images from 118 patients**, divided into two categories:
- **Normal cells**
- **Leukemia blast cells**

These cell images were segmented from microscopic scans. While they retain real-world imperfections like staining noise and illumination variation, most such distortions have been corrected. The dataset was collected and annotated by expert oncologists and represents real-world conditions with staining variability and lighting imperfections. These issues were partially corrected during image acquisition, preserving the dataset’s clinical realism.

**Objective**  
To build image classification models that can distinguish **normal** cells from **leukemic blasts**, a non-trivial task due to their morphological similarity. All ground truth labels were verified by an expert oncologist.

**Source**  
- **Kaggle Dataset**: [Leukemia Classification](https://www.kaggle.com/datasets/andrewmvd/leukemia-classification/data)
- **Dataset:** Gupta, A., & Gupta, R. (2019). *ALL Challenge dataset of ISBI 2019*. The Cancer Imaging Archive. [DOI: 10.7937/tcia.2019.dc64i46r](https://doi.org/10.7937/tcia.2019.dc64i46r)
- **License:** Not formally specified; usage is public with attribution requested.

**Citation**  
Gupta, A., & Gupta, R. (2019). *ALL Challenge dataset of ISBI 2019*. The Cancer Imaging Archive. https://doi.org/10.7937/tcia.2019.dc64i46r

**Related Publications**  
1. A. Gupta et al., “GCTI-SN: Geometry-Inspired Chemical and Tissue Invariant Stain Normalization of Microscopic Medical Images”, under review.  
2. R. Gupta et al., “Stain Color Normalization... in Multiple Myeloma,” IMW 2017.  
3. R. Duggal et al., “Overlapping Cell Nuclei Segmentation...” ICVGIP 2016.  
4. R. Duggal et al., “Segmentation of overlapping/touching WBC nuclei...,” AIIMS 2016.  
5. R. Duggal et al., “SD-Layer: Stain Deconvolutional Layer...,” MICCAI 2017. [DOI](https://doi.org/10.1007/978-3-319-66179-7_50)

## 1. `ODE.ipynb` — Deterministic Modeling

Implements a system of **Ordinary Differential Equations (ODEs)** to describe the average behavior of interacting cell populations (e.g., healthy vs. cancerous). Key features:
- Simulates long-term behaviors: homeostasis, extinction, overgrowth.
- Visualizes dynamics using time series and phase space plots.
- Provides interpretability of how parameters drive system behavior.

## 2. `Gillespie.ipynb` — Stochastic Simulation

Uses the **Gillespie algorithm** to simulate cell-level population changes under randomness. Features:
- Captures inherent biological variability.
- Generates multiple stochastic trajectories per regime.
- Labels data by outcomes (extinction vs. overgrowth) for ML use.

## 3. `ML.ipynb` — ML-based Classification

Applies supervised learning to classify the long-term behavior of a system using early time-series signals:
- Feature extraction and PCA for dimensionality reduction.
- Models include Random Forest, Ridge Classifier, KNN, SVM, and CNN.
- Evaluated with accuracy, confusion matrix, classification report, and ROC curves.
- Trained CNN model achieves ~85% validation accuracy in distinguishing regimes.

## Reference Publications
