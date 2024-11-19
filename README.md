# deep-learning-challenge
# Overview

The goal of this project was to analyze data from Alphabet Soup, a nonprofit organization, and build a binary classifier to predict whether funding applications
will be successful. Using a neural network model, we aimed to identify key features influencing success and refine the model to maximize accuracy, 
targeting a performance of 75%.

# Environment

This project was completed using the following environments:
1 Jupyter Notebook (Local Environment):
 • The initial implementation, including preprocessing, the first model and optimization, was developed locally in Jupyter Notebook to streamline development and testing.

2 Google Colab:
 • To align with the project instructions, the entire workflow was reproduced in Google Colab, ensuring consistent results. Both preprocessing and the first 
   model (AlphabetSoupCharity.h5) were successfully run in Colab, producing the same accuracy as in Jupyter Notebook.
 • Additionally, all optimization steps (e.g., Attempts 2, 3, and 4) were finalized and executed in Google Colab.
 
**Note:** Slight variations in results (e.g., accuracy and loss) were observed between Jupyter Notebook and Google Colab due to differences in runtime environments (e.g., GPU vs. CPU execution, floating-point precision, and library versions). These differences are minor and do not affect the overall conclusions or recommendations.

# Preprocessing and Training

1. Initial Implementation in Jupyter Notebook:
  • Data preprocessing included dropping non-beneficial columns (EIN, NAME, and later ASK_AMT), grouping rare categories, and encoding categorical variables.
  • The dataset was scaled using StandardScaler and split into training and testing sets.
  • The first model (AlphabetSoupCharity.h5) was trained and achieved an accuracy of 72.51%.
2. Reproduction in Google Colab:
  • The entire workflow, including preprocessing and training, was reproduced in Google Colab.
  • The first model yielded consistent accuracy and loss results.
    
# Data Preprocessing

The dataset provided contained various features, including categorical and numeric data. The following preprocessing steps were applied:
1. Dropped Non-Beneficial Columns:
  • Removed EIN and NAME as they are unique identifiers and do not contribute to predictions.
  • Dropped ASK_AMT after analysis showed it had minimal impact on model performance.
2. Grouped Rare Categories:
  • Grouped infrequent categories in APPLICATION_TYPE and CLASSIFICATION into “Other” to simplify feature representation:
  • Cutoff for APPLICATION_TYPE: Categories with fewer than 528 occurrences were grouped.
  • Cutoff for CLASSIFICATION: Categories with fewer than 1,883 occurrences were grouped.
3. Encoded Categorical Variables:
  • Used pd.get_dummies() to encode all categorical variables.
4. Scaled Numeric Features:
  • Applied StandardScaler to ensure numeric features were standardized for better model performance.
5. Split the Data:
  • Divided the dataset into training (80%) and testing (20%) subsets.
    
# Modeling

**Initial Model**
Architecture:
 • Two hidden layers:
 • Layer 1: 80 neurons, ReLU activation.
 • Layer 2: 30 neurons, ReLU activation.
Results:
 • Accuracy: 72.51%
 • Loss: 0.5584
Analysis:
 • Removing ASK_AMT simplified the feature set without degrading performance.
 • The low loss indicates stable predictions.

**Attempt 2**
Architecture:
 • Three hidden layers:
 • Layer 1: 80 neurons, ReLU activation.
 • Layer 2: 30 neurons, ReLU activation.
 • Layer 3: 15 neurons, ReLU activation.
Results:
 • Accuracy: 73.91%
 • Loss: 0.5449
Analysis:
 • Adding a third layer slightly improved accuracy.
 • Loss remained reasonable, indicating better generalization.584

**Attempt 3**
Architecture:
 • Four hidden layers:
 • Layer 1: 100 neurons, ReLU activation.
 • Layer 2: 50 neurons, ReLU activation.
 • Layer 3: 30 neurons, ReLU activation.
 • Layer 4: 15 neurons, ReLU activation.
Results:
 • Accuracy: 73.85%
 • Loss: 0.5450
Analysis:
 • Achieved the highest accuracy but with a higher loss, suggesting potential overfitting.
    
**Attempt 4**
Architecture:
 • Four hidden layers:
 • Layer 1: 120 neurons, ReLU activation.
 • Layer 2: 80 neurons, ReLU activation.
 • Layer 3: 40 neurons, ReLU activation.
 • Layer 4: 20 neurons, ReLU activation.
 • Dropout regularization (rate: 0.1).
Results:
 • Accuracy: 73.83%
 • Loss: 0.5449
Analysis:
 • Accuracy remained stable, but loss increased slightly compared to Attempt 3.

# Summary

Despite multiple optimizations, the neural network model did not achieve the target accuracy of 75%, reaching a maximum accuracy of 73.91% in the second 
optimization attempt. Various techniques were applied, including adding hidden layers, increasing neurons, and implementing dropout for regularization. 
However, the accuracy consistently plateaued around 73%, suggesting limitations in the current feature set or model configuration.

**1 Key Findings:

**Impact of Feature Selection:

Removing 'ASK_AMT' simplified the feature set without significantly impacting accuracy or loss. This step confirmed that the feature provided minimal 
predictive value in the current configuration.
    
** Effectiveness of Optimization:

Adding hidden layers and increasing neurons improved accuracy marginally, with Attempt 2 achieving the highest accuracy (73.91%). However, further 
architectural complexity yielded diminishing returns.
Dropout regularization helped mitigate overfitting but did not significantly boost accuracy.
    
** Comparison of Attempts:

Attempt 2 achieved the highest accuracy (73.91%) with a reasonable loss (0.5449), making it the best-performing model overall.
Attempt 3 had slightly lower accuracy (73.85%) but higher loss (0.5450), suggesting potential overfitting.
Attempt 4 provided a balance between accuracy (73.83%) and loss (0.5449) but did not outperform Attempt 2 in terms of generalization.

**2 Recommendations:

To achieve the target accuracy or improve performance further:

** Explore Alternative Algorithms:

- Test models such as Random Forests or XGBoost, which may better handle mixed feature types and class imbalance in the data.
- Consider simpler models like Logistic Regression with advanced feature engineering for interpretable results.

** Enhance Feature Engineering:

- Create interaction terms between features (e.g., combining APPLICATION_TYPE and CLASSIFICATION).
- Explore advanced encodings such as Target Encoding, which assigns probabilities based on the target variable.

** Select the Final Model:

- If prioritizing accuracy, Attempt 2 is the best choice.
- If balancing accuracy and loss is the priority, Attempt 4 is recommended as the final optimized model.



# Conclusion:

Although the neural network model exhibited consistent performance improvements through multiple optimizations, it was unable to surpass the 75% accuracy 
threshold. This indicates potential limitations in the dataset or the current neural network configuration. Future efforts should explore:
- Alternative Algorithms: To uncover hidden patterns that the neural network may not capture effectively.
- Advanced Feature Engineering: To enhance the predictive power of the feature set.
By combining these approaches, the model may better address the complexities of the data and achieve the desired performance goals.

# Files in Repository
AlphabetSoupCharity.ipynb: Notebook for the initial model.
AlphabetSoupCharity_Optimization.ipynb: Notebook for optimization attempts.
AlphabetSoupCharity_Attempt_1.h5: Model saved initial model.
AlphabetSoupCharity_Attempt_2.h5: Model saved optimized model.
AlphabetSoupCharity_Attempt_3_final.h5: Model saved optimized model
AlphabetSoupCharity_Attempt_4.h5: Model saved optimized model
AlphabetSoupCharity.ipynb_Colab: Notebook for the initial model in google colab.
AlphabetSoupCharity_Optimization_Colab.ipynb: Notebook for optimization attempts in google colab.
AlphabetSoupCharity_Attemp.h5: Saved initial model downloaded from google colab.
AlphabetSoupCharity_Attempt_2.h5: Saved optimized model downloaded from google colab..
AlphabetSoupCharity_Attempt_3_final.h5: Saved optimized model downloaded from google colab.
AlphabetSoupCharity_Attempt_4.h5: Saved optimized model downloaded from google colab.
README.md: This report.

