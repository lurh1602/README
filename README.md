# Dry Bean Identification

This project uses the Dry Bean Dataset from the UC Irvine Machine Learning Repository. The dataset contains geometric measurements of beans (e.g., area, perimeter, axis lengths), and the goal is to classify each bean into its correct type. I will be using Chat GTP for this assignment.



# Deliverable 1: Initial Prompt

I am working on a machine learning classification problem (with Chat GTP) using a dataset of dry beans. Each sample has geometric features (like area, perimeter, axis lengths, etc.) and a class label indicating the bean type. I want to build a model in MATLAB that predicts the bean type based on these features.

What machine learning method would be appropriate for this problem, and why? Also, how should I split the data and evaluate the model?



# Deliverable 2: The Random Forest Method

When describing the bean problem and the goals of this assignment to the LLM, it suggested I use the random forest method. I asked follow questions such as: How does the random forest method work; Why is the random forest method appropriate for this problem; and How can I make a confusion matrix with this imfortmation? Below is a summary (written by Chat GTP) of what it told me:

*The suggested method was Random Forest, which is an ensemble learning method based on decision trees.*

*A Random Forest works by:*

*- Creating many decision trees using random subsets of the data*

*- Each tree makes a prediction*

*- The final prediction is determined by a majority vote*

*“Random forests reduce overfitting by averaging multiple decision trees and improve predictive accuracy.”*

*Why Random Forest is appropriate:*

*- The problem is classification, which Random Forest handles well*

*- It works with multiple features without needing heavy preprocessing*

*- It handles correlated inputs better than a single decision tree*

*- It provides feature importance, which helps interpret the model*

*Validation Strategy*

*The standard approach is:*

*- Split the dataset into training (70%) and validation/testing (30%)*

*- Train the model on training data*

*- Evaluate using a confusion matrix on test data*

# Deliverable 3: Confusion Matrix



# Deliverable 4: Tuning the Model



# Deliverable 5: Feature Importance Plot
