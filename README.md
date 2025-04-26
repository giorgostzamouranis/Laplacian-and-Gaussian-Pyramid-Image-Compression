# Image Compression and Analysis Using Gaussian and Laplacian Pyramids

This project implements and analyzes the **Gaussian** and **Laplacian Pyramid** frameworks for image processing and compression, based on the techniques described in:
- "Pyramid Methods in Image Processing" by P. Burt (1981)
- "The Laplacian Pyramid as a Compact Image Code" by P. Burt and E. Adelson (1983)

The main objectives are:
- Building Gaussian and Laplacian pyramids from images.
- Reconstructing images from the pyramids and evaluating reconstruction quality.
- Performing quantization and analyzing its effects on compression and entropy.
- Studying how parameters like the generating kernel parameter 'a' and the pyramid depth influence the results.

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
   Discussion of key concepts including:
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
   - Testing with standard images (Lena and Camera).

---

## Implemented Functions

- **GKernel(a)**  
  Generates a 5x5 separable Gaussian-like kernel based on the parameter `a`.

- **GREDUCE(I, h)**  
  Applies convolution and downsampling to reduce the image resolution.

- **GPyramid(I, a, depth)**  
  Builds the Gaussian pyramid up to a specified depth.

- **GEXPAND(I, h)**  
  Upsamples the image by zero insertion and interpolation via convolution.

- **LPyramid(I, a, depth)**  
  Constructs the Laplacian pyramid from the Gaussian pyramid.

- **L_Pyramid_Decode(lpyr, a)**  
  Reconstructs the original image from a Laplacian pyramid.

- **L_Quantization(lpyr, bin_size)**  
  Applies uniform quantization across all Laplacian pyramid levels.

- **H_entropy(pyramid)**  
  Calculates the Shannon entropy for each pyramid level.

- **L_Quantization_by_levels(lpyr, bin_sizes)**  
  Performs level-dependent quantization using different bin sizes for each pyramid level.

---

## Experiments and Observations

- **Gaussian and Laplacian Pyramid Visualization**  
  Visual analysis of pyramid levels and reconstruction quality.

- **Effect of Kernel Parameter 'a'**  
  Tested values from 0.3 to 0.7. Best results in terms of reconstruction error and entropy observed around `a ≈ 0.5`.

- **Effect of Pyramid Depth**  
  Deeper pyramids slightly lower the entropy at higher levels without major loss of visual quality.

- **Quantization Analysis**  
  Larger bin sizes reduce entropy (better compression) but degrade image quality.

- **Entropy vs Parameter Plots**  
  Plots showing how entropy varies with kernel parameter 'a' and pyramid depth.

---

## Requirements

- Python 3.7+
- Libraries:
  - numpy
  - scipy
  - matplotlib
  - scikit-image
  - opencv-python
  - urllib

Install all requirements via pip:

```bash
pip install numpy scipy matplotlib scikit-image opencv-python
