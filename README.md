# Single Molecule Localisation Pipeline
![pipeline](https://github.com/ldeen22/Quantifying-Localisation-of-Single-Molecules/assets/163921964/74db88d6-3633-4007-975f-379a298731bb)


# Introduction 
This pipeline is designed to quantify the localisation accuracy of single molecules in microscopy data. It utilizes Python-based scripts to process TIFF-based microscopy images and calculate precision metrics based on Mortensen's formula.

# Motivation
This project presents compelling evidence highlighting a notable gap between experimental and theoretical precision outcomes, exceeding conventional margins. Despite the limited dataset comprising only five samples, these findings strongly suggest an inherent tendency towards overprecision in Mortensen’s formula, warranting further refinement. Delving into this concept is pivotal for the field of biophysics, where Mortensen’s formula holds significant sway in showcasing achievements in precision. Understanding and addressing this potential overestimation in precision is paramount for ensuring the accuracy and reliability of findings, ultimately advancing our comprehension and imaging capability of biological processes at the molecular level. Future work involves sharing the pipeline on GitHub to enable other researchers to assess their localisation accuracies. Collaborative efforts with partnering universities aim to organize data collection initiatives to amass sufficient single molecule localisation data. This collaborative approach seeks to empirically validate or challenge the observed disparity in Mortensen’s precision measurements, with the overarching goal of refining the formulation and proposing an enhanced, more precise formula, thus reshaping localisation accuracy within the field of biophysics.

# Pipeline Details
Python-Based: The pipeline is implemented in Python.

Repository: The pipeline repository is hosted on GitHub.

Input Requirements:
- Requires microscopy image movie in TIFF format.
- Requires background movie in TIFF format.

# Pipeline Workflow
Loading Data: The pipeline begins by loading TIFF-based files storing microscopy data and background images.

Region of Interest (ROI) Definition: The pipeline sets a window around the pixel deemed a "region of interest" (ROI). The ROI size is typically set to 15x15 pixels, optimized for each setup.

Bead Spot Detection: Bead spots within the ROI are detected using a Gaussian detection algorithm, with peaks stored in an array.

Gaussian Fitting: The raw bead data is fit to a 2D Gaussian to obtain absolute localisation coordinates.

Calculation of Precision Metrics: Mortensen's formula, along with additional parameters such as photon count and background, is calculated per single ROI across all frames. This allows for the calculation of theoretical Mortensen precision for all localisations.

Computing Experimental variance: The pipeline computes all potential distances between the fitted beads in the image and uses the variance in these distances is assessed to gauge the stability of the bead data.

Accessing Comprehensive Statistical Variances: By adopting this approach, the pipeline accesses a more comprehensive dataset of statistical variances than traditional methods.
Typically, only variances of bead coordinates are considered, but this expanded dataset encompasses variances for a factorial number of beads, offering a deeper understanding of the spatial dynamics within the sample.

# Note
To use the following datasets and pipeline, all files must be on the same folder on jupyter notebook
