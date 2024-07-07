##  Q6 UCI-HAR dataset. Compare DT, RF and Linear regression (yes, regression). For linear regression: each class label as an integer value. Say, 1: Sitting, 2:..., and so on. Use features extracted (from flattened out Linear Acceleration) using the TSFEL library. Compare the performance of these models. Is the usage of linear regression for classification justified? Why or why not?
---

### Comparison of Decision Tree (DT), Random Forest (RF), and Linear Regression (LR) 

Utilizing features extracted via the TSFEL library, we compare the performance of three models: Decision Tree, Random Forest, and Linear Regression. Below is a detailed evaluation:

### **Decision Tree (DT)**
- **Accuracy:** 0.8889
- **Precision:** 0.9048
- **Recall:** 0.8889
- **F1 Score:** 0.8897
- Confusion matrix:
  ![png](Q6-Q7_files/Q6-Q7_10_1.png)

DT showed commendable performance, with a well-balanced precision and recall. Despite some misclassifications, the confusion matrix illustrates a relatively balanced prediction across classes.

### **Random Forest (RF)**
- **Accuracy:** 0.9444
- **Precision:** 0.9484
- **Recall:** 0.9444
- **F1 Score:** 0.9443
- Confusion matrix:
  ![png](Q6-Q7_files/Q6-Q7_14_1.png)

RF surpassed DT in all metrics, underlining its effectiveness in this classification task. The higher scores across the board denote a robust and highly generalizable model. The confusion matrix further confirms its superior predictive capability, with minimal misclassifications.

### **Linear Regression (LR)**
- **Mean Absolute Error (MAE):** 12.8874
- **Mean Squared Error (MSE):** 494.5970
- **Root Mean Squared Error (RMSE):** 22.2395
- **R-squared (R2):** -168.5761
- **'Accuracy' (post rounding):** 0.1389

Applying LR to a classification task showcased its inadequacy, as reflected by poor performance metrics. The notably negative R-squared value suggests the model's predictive capability is significantly worse than a naive mean-based prediction. The 'accuracy', derived by rounding regression outputs, further emphasizes LR's unsuitability for classification purposes, starkly contrasting with the performances of DT and RF.

---


### Is it justified to use linear regression for classification task?

<b>Integral Class Labels</b>: In cases where classes are encoded as integers (e.g., 1, 2, 3, etc.), Linear Regression might interpret the problem as having an ordinal nature, implying that class 3 is somehow "more" of something than class 2 or 1. This interpretation is incorrect for nominal classes where no such ordinal relationship exists. For example, in the UCI HAR dataset, class labels represent activities like walking, sitting, or standing, which do not have a meaningful order that would justify a higher or lower numerical value.

<b>Output Interpretation</b>: Linear Regression outputs continuous values that don't map directly to class labels without additional steps (e.g., rounding or thresholding). These steps introduce arbitrary decision boundaries that may not reflect the true nature of the data.

<b>Model Assumptions</b>: Linear Regression assumes a linear relationship between features and the target variable. This assumption may not hold in classification problems where the decision boundary between classes can be non-linear or more complex.

<b>Sensitivity to Imbalance</b>: Linear regression can be disproportionately affected by outliers or imbalanced data, skewing predictions.

<b>Lack of Class Boundary Optimization</b>: Unlike classification algorithms, linear regression does not optimize for class boundaries, leading to poor performance on classification tasks.

The comparison clearly demonstrates that for classification tasks, especially with categorical outcomes like in the UCI-HAR dataset, models designed for classification (such as DT and RF) significantly outperform regression models not inherently suited for predicting discrete labels. Linear regression's poor performance underscores the importance of choosing an appropriate model based on the nature of the prediction task.

### Q7 Obtain the weights (take absolute values as weights can also be negative) of the linear regression model. Also, obtain the feature importance from the Random Forest model. Plot the weights obtained as a Bar plot. This will help you visualize what features are being prioritized by the models. Note that sum of feature importances for a Random Forest model is 1. you will have to bring the linear regression weights to the same scale. To do so you can divide the weights by the sum of all the weights. Plot the importance of the features in the same plot. Figure out the top 10 important features obtained from both the models and display their names. What do you infer?

### Normalized weights for linear regression

![png](Q6-Q7_files/Q6-Q7_26_0.png)
    


### Feature importance for random forest model

![png](Q6-Q7_files/Q6-Q7_28_0.png)
    


### Feature importance for both models in the same plot
    
![png](Q6-Q7_files/Q6-Q7_30_0.png)
    


### Top 10 features for both the models
    
![png](Q6-Q7_files/Q6-Q7_32_0.png)
    


### Inference

<b>Different Feature Sets</b>: The two models have identified largely distinct sets of top features, with no apparent overlap in the top 10 features listed. This suggests that the models may be leveraging different aspects of the data to make predictions. Linear Regression seems to focus on features related to "Wavelet energy" and "Wavelet absolute mean" across various signals, while Random Forest identifies a mix of "Wavelet energy," "Max," "Area under the curve," and "Absolute energy" features, indicating a diverse set of criteria for feature importance.

<b>Feature Engineering Importance</b>: The presence of "Wavelet" related features in both models' top lists underscores the potential value of feature engineering, especially time-frequency analysis methods like Wavelet transforms, in extracting informative features from time series data such as the UCI HAR dataset. It highlights the models' sensitivity to how data is represented.

<b>Model-Specific Interpretations</b>: The difference in top features reflects the inherent differences in how Linear Regression and Random Forest models interpret and use the data. Linear Regression, being a global model, assumes a linear relationship between features and the target. In contrast, Random Forest can capture non-linear relationships and interactions between features without explicitly modeling them, which might explain its broader set of top features.
