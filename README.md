# ML-Short-Projects
This repository contains a number of Machine Learning projects done by me as a part of Machine Learning (ES335) Course


## Image Reconstruction Using Random Fourier Features (RFF)
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







## Human Activity Recognition (Mini Project)

**Human Activity Recognition (HAR)** refers to the capability of machines to identify various activities performed by users. The knowledge acquired from these recognition systems is integrated into many applications where the associated device uses it to identify actions or gestures and performs predefined tasks in response.

### Dataset
For this assignment, publicly available dataset called UCI-HAR was used. The dataset contains data for 30 participants, each performing six activities while wearing a Samsung Galaxy S II smartphone on their waist. The smartphone's accelerometer and gyroscope captured 3-axial linear acceleration and 3-axial angular velocity.

### Preprocessing
- Used **CombineScript.py** to organize and sort accelerometer data, establishing separate classes for each category and compiling participant data.
- Used **MakeDataset.py** to read through all participant data and create a single dataset, then split it into train, test, and validation sets.

### Steps to Run Scripts
1. Placed **CombineScript.py** and **MakeDataset.py** in the same folder containing the UCI dataset.
2. Ran **CombineScript.py** and provided paths to the test and train folders in the UCI dataset.
3. Ran **MakeDataset.py** and provided the path to the Combined folder to create a dataset containing train, test, and validation sets.

### Project Tasks and Results
1. **Plotted Waveforms**: Plotted the waveform for data from each activity class. Identified differences and similarities between the activities. This helped determine if the model could classify activities based on the data.
2. **Static vs. Dynamic Activities**: Analyzed whether a machine learning model is necessary to differentiate between static (laying, sitting, standing) and dynamic activities (walking, walking_downstairs, walking_upstairs) based on linear acceleration. Concluded that the linear acceleration data showed significant differences between static and dynamic activities.
3. **Decision Tree Model**: Trained a Decision Tree using the train set and reported accuracy and confusion matrix using the test set. Achieved satisfactory classification performance.
4. **Varying Depths of Decision Tree**: Trained Decision Trees with varying depths (2-8) and reported accuracy and confusion matrix using the test set. Observed that accuracy varied with depth, and plotted the accuracies to explain the results.
5. **PCA on Total Acceleration**: Used PCA to compress acceleration time series into two features and plotted a scatter plot. Then used TSFEL to create features, performed PCA, and plotted a scatter plot to visualize different class activities. Found that TSFEL features provided better separation between classes.
6. **Featurized Decision Tree**: Trained a Decision Tree using features obtained from TSFEL. Reported accuracy and confusion matrix using the test set. Found that featurizing worked better than using raw data. Compared accuracies obtained in Q4 with those obtained using the featurized train set and plotted the results.
7. **Model Performance Analysis**: Identified participants/activities where the model performed poorly and analyzed reasons for the poor performance. Found that some activities had overlapping feature distributions, leading to misclassifications.
8. **Deployment**: Collected data using Physics Toolbox Suite, ensuring at least 10 seconds per file for training. Trained the model on the UCI dataset and tested it on the collected data. Reported accuracy and confusion matrix, and explained the results. Ensured consistent phone placement and alignment during activities to maintain data quality.






## Comparing Decision Tree, Random Forest, and Linear Regression on UCI-HAR dataset

* This project compares the performance of Decision Tree, Random Forest, and Linear Regression models on the UCI Human Activity Recognition (HAR) dataset. It involves extracting features using the TSFEL library, evaluating the models' effectiveness, and analyzing feature importance. The project aims to determine the suitability of linear regression for classification tasks and identify the top features prioritized by each model.


## Contributors
* Dewansh Kumar
* Bhoumik Patidar
