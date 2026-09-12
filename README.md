# GMM-Based Anomaly Detection

A machine learning project that implements a **Gaussian Mixture Model (GMM)** from scratch using the **Expectation-Maximization (EM)** algorithm to detect anomalous data points.

## Overview

The project learns the distribution of normal data by estimating:

- **Means (μ)**
- **Covariances (Σ)**
- **Mixing weights (π)**

After training, the model calculates a probability score for each data point. Points with very low probability are treated as anomalies.

## How It Works

The GMM is trained using the EM algorithm:

1. **E-Step:** Calculate the probability (responsibility) of each point belonging to each Gaussian component.
2. **M-Step:** Update the means, covariances, and mixing weights based on these probabilities.
3. Repeat the process for the specified number of iterations.

The implementation also uses covariance regularization to help prevent singular covariance matrices.

## Dataset

The notebook generates synthetic 2D data containing:

- Two normal Gaussian clusters with 100 points each.
- Four manually defined anomalous points located far from the normal clusters.

The GMM is trained only on the normal data.

## Results

The trained model successfully learns two Gaussian components and produces probability scores for both normal and anomalous samples.

Normal samples receive relatively higher likelihood scores, while the anomalous points receive very low scores, allowing them to be identified as anomalies.

## Visualization

The project includes a visualization showing:

- Normal data points
- Anomalies
- The learned GMM means

This makes it easy to see that the anomalous points are located far from the normal clusters.