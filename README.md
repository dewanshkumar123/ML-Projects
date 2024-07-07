# ML-Short-Projects
This repository contains a number of Machine Learning projects done by me as a part of Machine Learning (ES335) Course


### Image Reconstruction Using Random Fourier Features (RFF)
**a.** Superresolution
* Performed superresolution on the cropped image from the notebook, enhancing its resolution by a factor of 2 using Random Fourier Features (RFF).
* Displayed a qualitative comparison of the original and reconstructed images.
  
**b.** Quantitative Comparison
* Used a 400x400 image as the ground truth high-resolution image.
* Resized it to a 200x200 image as the input image.
* Applied RFF + Linear regression to increase the resolution to 400x400 (predicted high-resolution image).
* Computed the RMSE and Peak SNR metrics to compare the predicted high-resolution image with the ground truth.
  
**c.** Completing Image with Random Missing Data
* Applied RFF to complete the image with varying percentages (10%, 20%, ..., 90%) of data missing randomly.
* Randomly removed portions of the data, trained the model on the remaining data, and predicted on the entire image.
* Displayed the reconstructed images for each missing data percentage and computed the RMSE and Peak SNR metrics for each case.
* Concluded the effectiveness of RFF in image reconstruction with different levels of missing data.
