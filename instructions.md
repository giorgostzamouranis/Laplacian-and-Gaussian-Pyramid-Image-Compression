# 1st Individual Assignment
## Image and Video Technology and Analysis

---

## 1. Theoretical Part (20 points)

Read the article **"The Laplacian Pyramid as a Compact Image Code"** by Burt, P. J. and Adelson, E. H., and briefly answer (in 1 paragraph) the following:

- **a)** How does the value of 'a' affect the Gaussian pyramid?
- **b)** What do we define as entropy? Calculate the maximum entropy value that a grayscale image can have.
- **c)** How does the choice of bin size affect the result of quantization?
- **d)** Explain how the number of pyramid levels affects the quantization.

---

## 2. Laboratory Part (80 points)

Base your implementation on the notebooks:
- `3.4.3330.8_Lab_3.2_Pyramids_Gaussian_Laplacian.ipynb`
- `3.4.3330.8_Lab_3.1_Sampling.ipynb`

to create the following core functions for image pyramids:

---

### A. Algorithm Implementation (30 points)

Implement the following functions:

1. `h = GKernel(a)`:  
   Creates a generating kernel dependent on the parameter 'a' (see page 533 of the article).

2. `I_out = GREDUCE(I, h)`:  
   According to equation (1) (page 533 of the article).

3. `G = GPyramid(I, a, depth)`:  
   Receives an input image `I`, the parameter `a`, and the desired pyramid depth `depth`, and returns the Gaussian pyramid (saving it internally).  
   It must call the functions `GKernel(a)` and `GREDUCE(I,h)`.

4. `I_out = GEXPAND(I, h)`:  
   According to equation (2) (page 534 of the article).

5. `L = LPyramid(I, a, depth)`:  
   Returns the Laplacian pyramid of image `I` (use `GPyramid` function).

6. `I_out = L_Pyramid_Decode(L, a)`:  
   Returns the decoded (reconstructed) image `I_out`, taking as input the Laplacian pyramid `L` and the parameter `a` used during pyramid construction.

7. `L_Quantization`:  
   According to equation (5) (page 538 of the article).

---

### B. Algorithm Testing (50 points)

1. Verify your implementations of the `LPyramid` and `L_Pyramid_Decode` functions using the **Lena** and **Camera** images.  
   Your functions must work correctly for both color and grayscale images.

---

Useful links:
- [Laplacian Pyramid Paper (pyramid83.pdf)](http://persci.mit.edu/pub_pdfs/pyramid83.pdf)
- [Google Colab Notebook - Lab 3.2](https://colab.research.google.com/drive/17BI_Yr0bENExHgMVIrfCDwFZcrH4yTsT)
- [Google Colab Notebook - Lab 3.1](https://colab.research.google.com/drive/1FktSsDxcCCofk8TOQmHaQdS8kbDs9mu7)
- [Lena image](http://www.image.ntua.gr/~tpar/LABimage/lena.png)
- [Camera image](https://scikit-image.org/docs/dev/api/skimage.data.html#skimage.data.camera)

---

2. Display the original and the decoded image using different values of `a`, ranging from `[0.3, ..., 0.7]`.

3. Display the original and the decoded image using different values of `depth`, ranging from `[3, ..., 6]`.

4. Compute the entropy and present the corresponding plots for different values of `a` and `depth`, for each image, and provide appropriate commentary.

5. Identify the optimal value of `a` based on the entropy for each level of the Laplacian pyramid, for each image.

6. For the optimal `a` value found in the previous step, quantize the Lena and Camera images using different bin sizes (perform 2 different experiments per image).

---

