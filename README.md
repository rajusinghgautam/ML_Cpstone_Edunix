# ML_Cpstone_Edunix

This project involves predicting an individual's gender using dental metrics, such as inter-canine distances and canine widths, which are essential in forensic investigations where identification is needed. The project uses machine learning models to analyze these dental features and determine the gender, aiding forensic medicine.

1. **Data Preprocessing**:
   **Objective**: Clean the dataset and prepare it for analysis.
   **Handled Missing Values**: We identified missing values, particularly in the `Sample ID` column, which we dropped entirely due to the lack of data. We also filled missing values in numerical columns using the mean.
  **Categorical Data Encoding**: Converted the `Gender` column (Male/Female) into numerical values using `LabelEncoder`.
  **Normalization**: Applied normalization to the independent variables so that all values fell within a similar range, avoiding dominance of any particular feature.

 2. **Exploratory Data Analysis (EDA)**:
   - **Objective**: Understand the data distribution and relationships between features.
   - **Steps**:
     - Plotted **histograms** to observe the distribution of each feature.
     - Created a **correlation heatmap** to identify relationships between dental features and detect multicollinearity issues, helping in model refinement by dropping highly correlated features if necessary.

 3. **Model Building**:
   - **Objective**: Build machine learning models to predict gender using dental metrics.
     - Split the data into **training** and **test sets** (80% train, 20% test).
     - Trained three different models: **Logistic Regression**, **Decision Tree**, and **Random Forest** classifiers.
     - Evaluated the models using **accuracy** and **confusion matrices** to check how well each model performed.

#### 4. **Model Evaluation**:
   - **Objective**: Assess the model performance using evaluation metrics.
     - Calculated the **accuracy** for each model:
       - Logistic Regression: 87%
       - Decision Tree: 88%
       - Random Forest: 90%
     - Plotted the **ROC curves** and calculated **AUC scores**:
       - Random Forest showed the highest AUC of **0.91**, indicating it had the best overall performance.
     - The **confusion matrices** revealed that the models performed well at correctly classifying the genders with few errors.

#### 5. **Final Conclusion**:
   - Based on model evaluation, the **Random Forest classifier** was identified as the best-performing model in this task due to its high accuracy and AUC score.
   - This model can be used in forensic contexts to accurately predict gender based on dental metrics.

### Challenges and Solutions:

1. **Handling Missing Values**:
   - **Challenge**: The `Sample ID` column had entirely missing values, and other features had sporadic missing values.
   - **Solution**: We dropped the `Sample ID` column and filled missing values in numerical columns using the mean, ensuring no loss of crucial information.

2. **Data Imbalance**:
   - **Challenge**: During EDA, we noticed slight gender imbalances in the dataset, which can impact model performance.
   - **Solution**: Although the imbalance was minor, we carefully monitored model performance using **confusion matrices** to ensure it didn't skew the results.

3. **Feature Multicollinearity**:
   - **Challenge**: Some features were highly correlated, which can degrade model performance.
   - **Solution**: We analyzed the correlation matrix and considered dropping or transforming highly correlated features. In this case, the models handled multicollinearity well, so no features were removed.

4. **Model Selection**:
   - **Challenge**: Determining the best model for this dataset required comparing multiple models.
   - **Solution**: By evaluating models using accuracy, confusion matrices, and ROC/AUC, we identified the **Random Forest** as the most robust model for this task.

### Conclusion:

This project utilized dental metrics to predict gender using machine learning models in Python. Through thorough data preprocessing, exploratory data analysis, model building, and evaluation, we developed an accurate and reliable model to assist forensic experts. The **Random Forest classifier** was the best-performing model, achieving an accuracy of **90%** and an AUC of **0.91**. This model can be applied in real-world forensic scenarios for gender identification based on dental data.
