# CIFAR-10 Image Generation with VAE and DCGAN

## Overview

This project explores deep generative models for generating CIFAR-10-like images. Two approaches were developed and evaluated:

* Variational Autoencoder (VAE)
* Deep Convolutional Generative Adversarial Network (DCGAN)

The baseline models were compared using both quantitative and qualitative evaluation. The stronger baseline was then systematically improved and used to generate a final set of 1,000 CIFAR-10-like images.

## Dataset

The project uses the **CIFAR-10** dataset, which contains:

* 60,000 RGB images
* Image size: 32 × 32 × 3
* 10 balanced classes
* 45,000 training images
* 5,000 validation images
* 10,000 test images

Model-specific image normalisation was applied to match the output activation used by each generative model.

## Approach

### 1. Variational Autoencoder (VAE)

A convolutional VAE was developed as a baseline generative model. The encoder maps input images to a latent probability distribution, while the decoder reconstructs images from sampled latent vectors.

### 2. Deep Convolutional GAN (DCGAN)

A baseline DCGAN was developed and compared against the VAE. The generator learns to create synthetic images while the discriminator distinguishes generated images from real CIFAR-10 images.

### 3. Systematic DCGAN Improvement

The DCGAN baseline was selected for further improvement based on the experimental comparison.

Several controlled experiments were conducted to investigate model performance, including architectural and training-related changes. The improved model was evaluated using the same validation-based evaluation procedure to support fair comparison.

## Evaluation

The models were evaluated using:

* Fréchet Inception Distance (FID)
* Average Pairwise Mean Squared Error (MSE)
* Training diagnostics
* Qualitative inspection of generated images

The baseline comparison showed that the DCGAN achieved a lower validation FID than the baseline VAE, while producing sharper and more structured images.

## Results

The baseline DCGAN achieved a validation FID of **96.9811**, compared with **236.8284** for the baseline VAE.

The DCGAN was therefore selected for systematic improvement and further evaluation.

The final model was used to generate **1,000 CIFAR-10-like images**.

## Tools & Technologies

* Python
* TensorFlow / Keras
* NumPy
* Pandas
* SciPy
* Scikit-learn
* Matplotlib
* Jupyter Notebook

## Repository Contents

* `DELE_CA2_PartA.ipynb` — Main implementation and experiments
* `Presentation.pdf` — Project presentation
* `requirements.txt` — Python package dependencies

## Reproducibility

A fixed random seed was used to improve the reproducibility of data sampling, model initialisation, and generated results. However, generative model training may still vary slightly across different computing environments.

## Project Context

This project was completed as **Part A of ST1504 Deep Learning CA2** at Singapore Polytechnic.
