# deep-learning-challenge

# Overview

The goal of this project was to analyze data from Alphabet Soup, a nonprofit organization, and build a binary classifier to predict whether funding 
applications would be successful. Using a neural network model, the aim was to identify key features influencing success and optimize the model to maximize 
accuracy, targeting a performance of 75%.

**Environment**

This project was completed using the following environments:

1. Jupyter Notebook (Local Environment):

- Initial implementation, preprocessing, and first model training were developed locally to streamline testing.

2. Google Colab:

- The entire workflow, including preprocessing, training, and optimization steps, was reproduced in Colab for consistency.
- Results varied slightly due to differences in runtime environments (e.g., GPU vs. CPU execution and library versions), but conclusions remained unaffected.

**Data Preprocessing**

The dataset contained various categorical and numeric features. The following steps were applied:

1. Dropped Non-Beneficial Columns:
 - Removed EIN and NAME as they are unique identifiers and do not contribute to predictions.

2. Grouped Rare Categories:
 - APPLICATION_TYPE: Categories with fewer than 528 occurrences were grouped into "Other."
 - CLASSIFICATION: Categories with fewer than 1,883 occurrences were grouped into "Other."
 
3. Encoded Categorical Variables:
 - Used pd.get_dummies() to one-hot encode all categorical features.
 
4. Scaled Numeric Features:
 - Applied StandardScaler to standardize numeric features.
 
5. Split the Data:
Divided the dataset into training (80%) and testing (20%) subsets.

**Modeling**
**Initial Model**

- Architecture:
 - Two hidden layers:
  - Layer 1: 8 neurons, ReLU activation.
  - Layer 2: 5 neurons, ReLU activation.
  
**Results:**
 - Accuracy: 72.65%
 - Loss: 0.5560

**Analysis:**
 - Provided a solid baseline with good generalization but left room for improvement.
 
**Optimization Attempts**
**Attempt 2**

- Architecture:
 - Three hidden layers:
  - Layer 1: 80 neurons, ReLU activation.
  - Layer 2: 30 neurons, ReLU activation.
  - Layer 3: 15 neurons, ReLU activation.
  - Dropout regularization (rate: 0.2).

**Results:**
 - Accuracy: 72.90%
 - Loss: 0.5733

**Analysis:**
 - Marginal accuracy improvement with dropout, but performance plateaued.

**Attempt 3**

- Architecture:
 - Four hidden layers:
  - Layer 1: 100 neurons, ReLU activation.
  - Layer 2: 50 neurons, ReLU activation.
  - Layer 3: 30 neurons, ReLU activation.
  - Layer 4: 15 neurons, ReLU activation.
  - Dropout regularization (rate: 0.1).

- Results:
 - Accuracy: 72.61%
 - Loss: 0.5941

- Analysis:
 - Higher complexity resulted in diminishing returns and potential overfitting.
 
**Attempt 4**

- Architecture:
 - Four hidden layers:
  - Layer 1: 120 neurons, ReLU activation.
  - Layer 2: 80 neurons, ReLU activation.
  - Layer 3: 40 neurons, ReLU activation.
  - Layer 4: 20 neurons, ReLU activation.
  - Dropout regularization (rate: 0.2) and L2 regularization.

- Results:
 - Accuracy: 72.08%
 - Loss: 0.5792

- Analysis:
 - L2 regularization stabilized the loss but did not improve accuracy.
 
**Google Colab Results**

To validate the workflow, the entire process was reproduced in Google Colab. Results varied slightly due to runtime differences but remained consistent in overall performance and conclusions.

**Colab Results:**

- **Attempt 1**:
  - Accuracy: 72.68%
  - Loss: 0.5559

- **Attempt 2**:
  - Accuracy: 73.04%
  - Loss: 0.5746

- **Attempt 3**:
  - Accuracy: 72.49%
  - Loss: 0.5916

- **Attempt 4**:
  - Accuracy: 72.17%
  - Loss: 0.5793

**Visualizations**
To compare the performance across all attempts, accuracy and loss visualizations were generated:

### Local Visualizations

Accuracy Across Attempts

![accuracy_plot](https://github.com/user-attachments/assets/7d7706a8-9e3e-4723-a0cb-1e95a87ad3ab)

Loss Across Attempts

![loss_plot](https://github.com/user-attachments/assets/80f4de31-739a-41f7-8e1d-5c38e44c1351)

### Colab Visualizations

Accuracy Across Attempts

![accuracy_plot](https://github.com/user-attachments/assets/a12f6c95-e418-43d3-a6cd-fc5a9937eff1)

Loss Across Attempts

![loss_plot](https://github.com/user-attachments/assets/fa9ca2ab-e0a8-450c-b964-ac48a8f2c92d)

**Summary**
**Key Findings**

- Minor performance differences were observed between local and Colab environments, but the highest accuracy (73.04%) was achieved in Attempt 2 in Colab.

1. Impact of Model Complexity:
 - Adding layers and increasing neurons improved accuracy marginally but led to diminishing returns beyond Attempt 2.

2. Regularization:
 - Dropout and L2 regularization reduced overfitting but did not significantly boost accuracy.

3. Final Performance:
 - The highest accuracy achieved was 72.90% (Attempt 2), falling short of the target accuracy of 75%.

**Recommendations**
1. Explore Alternative Models:
 - Use Random Forests or XGBoost to better handle mixed feature types and class imbalance.
 - Test Logistic Regression with advanced feature engineering for interpretability.

2. Feature Engineering:
 - Create interaction terms (e.g., between APPLICATION_TYPE and CLASSIFICATION).
 - Explore advanced encoding techniques like Target Encoding.

**Conclusion**
While the neural network provided consistent performance across all attempts, it fell short of the target accuracy, indicating potential limitations in the 
dataset or model configuration. Future work should focus on:

 - Leveraging alternative algorithms.
 - Enhancing feature engineering to boost predictive power.

By implementing these recommendations, future models can better address the data's complexities and achieve the desired performance goals.


# Files in Repository
AlphabetSoupCharity.ipynb: Notebook for the initial model.
AlphabetSoupCharity_Optimization.ipynb: Notebook for optimization attempts.
AlphabetSoupCharity.h5: Model saved initial model.
AlphabetSoupCharity_Attempt_2.h5: Model saved optimized model.
AlphabetSoupCharity_Attempt_3.h5: Model saved optimized model
AlphabetSoupCharity_Attempt_4.h5: Model saved optimized model
AlphabetSoupCharity.ipynb_Colab: Notebook for the initial model in google colab.
AlphabetSoupCharity_Optimization_Colab.ipynb: Notebook for optimization attempts in google colab.
AlphabetSoupCharity_Attemp.h5: Saved initial model downloaded from google colab.
AlphabetSoupCharity_Attempt_2.h5: Saved optimized model downloaded from google colab..
AlphabetSoupCharity_Attempt_3.h5: Saved optimized model downloaded from google colab.
AlphabetSoupCharity_Attempt_4.h5: Saved optimized model downloaded from google colab.
README.md: This report.

