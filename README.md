# Laplacian Pyramid Image Compression and Analysis

This project implements and analyzes the **Gaussian** and **Laplacian Pyramid** frameworks for image processing and compression, based on the classic paper by Burt and Adelson ("The Laplacian Pyramid as a Compact Image Code", 1983).

The main objectives of the project are:
- Building Gaussian and Laplacian pyramids from images.
- Reconstructing images from the pyramids and evaluating reconstruction quality.
- Performing quantization and analyzing the effects on compression and entropy.
- Studying how parameters (such as the generating kernel parameter 'a' and the depth of the pyramid) influence the results.

---

## Table of Contents

- [Project Structure](#project-structure)
- [Implemented Functions](#implemented-functions)
- [Experiments and Observations](#experiments-and-observations)
- [Requirements](#requirements)

---

## Project Structure

The project is divided into two main parts:

1. **Theoretical Part**  
   Explanation of key concepts including:
   - Effect of the kernel parameter 'a' on the Gaussian pyramid.
   - Definition and calculation of entropy.
   - Impact of bin size on quantization.
   - Influence of pyramid depth on quantization precision.

2. **Laboratory Part**  
   Full Python implementation including:
   - Construction of Gaussian and Laplacian pyramids.
   - Image reconstruction from pyramids.
   - Quantization experiments.
   - Entropy calculation and analysis.
   - Testing using standard images (Lena and Camera).

---

## Implemented Functions

- **GKernel(a)**  
  Generates a 5x5 separable Gaussian-like kernel based on parameter `a`.

- **GREDUCE(I, h)**  
  Applies convolution and downsampling to reduce image resolution.

- **GPyramid(I, a, depth)**  
  Builds a Gaussian pyramid up to the specified depth.

- **GEXPAND(I, h)**  
  Upsamples the image by inserting zeros and interpolating via convolution.

- **LPyramid(I, a, depth)**  
  Constructs the Laplacian pyramid from the Gaussian pyramid.

- **L_Pyramid_Decode(lpyr, a)**  
  Reconstructs the original image from a Laplacian pyramid.

- **L_Quantization(lpyr, bin_size)**  
  Uniformly quantizes each level of a Laplacian pyramid.

- **H_entropy(pyramid)**  
  Calculates the Shannon entropy of each pyramid level.

- **L_Quantization_by_levels(lpyr, bin_sizes)**  
  Performs level-dependent quantization with different bin sizes at each level.

---

## Experiments and Observations

- **Gaussian and Laplacian Pyramid Visualization**  
  Visual analysis of the pyramid levels and reconstruction quality.

- **Effect of Kernel Parameter 'a'**  
  Tested values from 0.3 to 0.7; found that `a ≈ 0.5` gives the best entropy and reconstruction quality.

- **Effect of Pyramid Depth**  
  Observed that deeper pyramids slightly lower the entropy at higher levels, without major quality loss.

- **Quantization Analysis**  
  Showed how larger bin sizes degrade visual quality but significantly reduce entropy (compression efficiency).

- **Entropy vs Parameter Plots**  
  Plots showing how entropy varies with different values of `a` and different pyramid depths.

---

## Requirements

- Python 3.7+
- Libraries:
  - numpy
  - scipy
  - matplotlib
  - scikit-image
  - OpenCV (`cv2`)
  - urllib

Install requirements via pip:

```bash
pip install numpy scipy matplotlib scikit-image opencv-python
