# Dry Bean Identification

This project uses the Dry Bean Dataset from the UC Irvine Machine Learning Repository. The dataset contains geometric measurements of beans (e.g., area, perimeter, axis lengths), and the goal is to classify each bean into its correct type. I will be using Chat GTP for this assignment.



# Deliverable 1: Initial Prompt

I am working on a machine learning classification problem (with Chat GTP) using a dataset of dry beans. Each sample has geometric features (like area, perimeter, axis lengths, etc.) and a class label indicating the bean type. I want to build a model in MATLAB that predicts the bean type based on these features.

What machine learning method would be appropriate for this problem, and why? Also, how should I split the data and evaluate the model?



# Deliverable 2: The Random Forest Method

When describing the bean problem and the goals of this assignment to the LLM, it suggested I use the random forest method. I asked follow questions such as: How does the random forest method work; Why is the random forest method appropriate for this problem; and How can I make a confusion matrix with this imfortmation? Below is a summary (written by Chat GTP) of what it told me:

**The suggested method was Random Forest, which is an ensemble learning method based on decision trees.**

**A Random Forest works by:**
- Creating many decision trees using random subsets of the data
- Each tree makes a prediction
- The final prediction is determined by a majority vote
  
“Random forests reduce overfitting by averaging multiple decision trees and improve predictive accuracy.”

**Why Random Forest is appropriate:**
- The problem is classification, which Random Forest handles well
- It works with multiple features without needing heavy preprocessing
- It handles correlated inputs better than a single decision tree
- It provides feature importance, which helps interpret the model

**Validation Strategy**

*The standard approach is:*
- Split the dataset into training (70%) and validation/testing (30%)
- Train the model on training data
- Evaluate using a confusion matrix on test data



# Deliverable 3: Confusion Matrix


<img width="1447" height="633" alt="MCEN 3030 LLM project 1" src="https://github.com/user-attachments/assets/e11a19ee-b2d3-45f4-9dd9-b3dbce8abedf" />


Confusion Matrix Observations/Discussions:
- The first model used n=100 trees.
- The majority of the bean predictions fall along the diagonal of the matrix, meaning the model was fairly accurate.
- MATLAB reported the accuracy of the model to be 91.65%.
- The Bombay bean was the most accurately predicted bean, with only one bean incorrectly predicted to be a Bombay bean.
- The SIRA bean was the least accurate predicted bean, with 122 beans inaccurately predicted to be SIRA beans.
- The Dermason and SIRA beans have the most similar properties and were frequently mixed up (162 misidentified SIRA/Dermason beans for each other)



# Deliverable 4: Tuning the Model

My initial accuracy was already pretty decent. It was significantly higher than 80%, which was stated in the prompt that the model may never resonably get above. Neither me or the LLM could come up with significant ways to improve the model, so I decided to shoot for a smaller improvement (~1% more accuracy). This was achieved by adjusting hyperparameters, such as the number of trees and the minimum leaf size, and normalizing the data.
The changes made to the code include:
- Increasing the number of trees from 100 to 300
- Creating a minimum leaf size of 5 to avoid overfitting (memorizing the data)
- And normalizing the x-data so bean features were taking into account more evenly


<img width="1330" height="632" alt="MCEN 3030 project 3" src="https://github.com/user-attachments/assets/af619b0e-9582-4a2e-b840-691c3e89ac69" />


Observations/Comparing the models:
- The accuracy of the refined model was 92.82%, a 1.17% increase from the previous model
- Only 98 beans were misidentified as SIRA beans (a 24 bean improvement)
- No beans were misidentified as Bombay (though one Bombay bean was misidentified as a Barbunya)
- Though the two beans that were the most switched up were the SIRA and Dermason beans, the improved model was better at distinguishing between them (a 31 bean improvement)



# Deliverable 5: Feature Importance Plot


<img width="1293" height="638" alt="MCEN 3030 project 4" src="https://github.com/user-attachments/assets/1da311d3-ca4e-46a8-8038-7acceb556d7f" />


Observations:
- Roundness, compactness, and shape factor 4 were the three most important features when identifying bean types.
- Eccentricity, equivalent diameter, and shape factor 3 were not relevant at all when identifying bean types.
- Area, perimeter, and major axis length were moderately important for sorting beans.
