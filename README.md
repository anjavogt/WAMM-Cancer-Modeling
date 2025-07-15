# Cancer Progression Modeling

This repository presents a multi-perspective approach to modeling and classifying cancer cell population dynamics. It combines **deterministic ODE modeling**, **stochastic simulation (Gillespie algorithm)**, and **machine learning (ML)** techniques to better understand the conditions under which colon cell populations, stem cells, transit amplifying (TA), and fully differentiated (FD), cells go extinct or grow uncontrollably.

### Authors: 
Rebecca Wang: lufanw@uw.edu, Alexis Georgiades: alexisg8@uw.edu, Anja Vogt: anjav@uw.edu

## Project Overview

This project was developed as part of a research project in the AMATH Department at the University of Washington (Spring 2025). The goal is to simulate, analyze, and predict cell population changes under varying biological conditions using computational and data-driven methods. We begin by reproducing and expanding upon the colorectal cancer models described by Mamis et al, https://royalsocietypublishing.org/doi/full/10.1098/rspb.2023.1020. Then we try different ML classifiers to work at seperating malignant vs. non-malignant cells from a public data set.

## Dataset Information

**About the Dataset**  
This dataset focuses on one of the most prevalent forms of childhood cancer: **Acute Lymphoblastic Leukemia (ALL)**. It consists of **15,135 images from 118 patients**, divided into two categories:
- **Normal cells**
- **Leukemia blast cells**

These cell images were segmented from microscopic scans. While they retain real-world imperfections like staining noise and illumination variation, most such distortions have been corrected. The dataset was collected and annotated by expert oncologists and represents real-world conditions with staining variability and lighting imperfections. These issues were partially corrected during image acquisition, preserving the dataset’s clinical realism.

**Objective**  
To build image classification models that can distinguish **normal** cells from **leukemic blasts**, a non-trivial task due to their morphological similarity. All ground truth labels were verified by an expert oncologist.

**Source**  
- **Dataset:** Gupta, A., & Gupta, R. (2019). *ALL Challenge dataset of ISBI 2019*. The Cancer Imaging Archive. [DOI: 10.7937/tcia.2019.dc64i46r](https://doi.org/10.7937/tcia.2019.dc64i46r)
- **License:** The dataset is publicly available via Kaggle and The Cancer Imaging Archive. No formal license was specified, but users are encouraged to cite the authors when using the dataset in research or applications.

## 1. `ODE.ipynb` — Deterministic Modeling

Implements a system of **Ordinary Differential Equations (ODEs)** to describe the average behavior of interacting cell populations (e.g., TA vs FD cells). Key features:
- Simulates long-term behaviors: homeostasis, extinction, overgrowth.
- Visualizes dynamics using time series, phase space plots, and stability analyses.
- Provides interpretability of how parameters drive system behavior.

## 2. `Gillespie.ipynb` — Stochastic Simulation

Uses the **Gillespie algorithm** to simulate cell-level population changes under randomness. Features:
- Captures inherent biological variability.
- Generates multiple stochastic trajectories.

## 3. `ML.ipynb` — ML-based Classification

Implements a complete pipeline of image-based leukemia classification, combining PCA for dimensionality reduction, centroid, and traditional classifiers while maintaining generalization and leveraging real-world medical image imperfections.
- Feature extraction and PCA for dimensionality reduction.
- Models include Random Forest, Ridge Classifier, KNN, SVM, and CNN.
- Evaluated with accuracy, confusion matrix, classification report, and ROC curves.
- Trained CNN model achieves ~85% validation accuracy in distinguishing regimes.

## Publication Citation
- **Dataset Source:** [Leukemia Classification Dataset](https://www.kaggle.com/datasets/andrewmvd/leukemia-classification/data) on Kaggle – curated from the ALL Challenge dataset used in ISBI 2019.
- Cole, L. (2020, April 14). Gillespie Algorithm. Lewis Cole Blog. https://lewiscoleblog.com/gillespie-algorithm
- K. Mamis et al., “Stochastic model for cell population dynamics quantifies homeostasis in colonic crypts and its disruption in early tumorigenesis,” Proceedings of the Royal Society B: Biological Sciences, 2023. DOI: 10.1098/rspb.2023.1020
