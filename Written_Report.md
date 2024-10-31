## **Alphabet Soup Deep Learning Model Report**

### **1. Overview of the Analysis**

The goal of this analysis was to create a neural network model to help Alphabet Soup, a fictional charity organization, predict the likelihood of success for funding applications. By analyzing past application data, this model can provide insights that may guide the charity in making data-driven decisions about future funding requests. This report presents the model's structure, tuning processes, performance, and recommendations.

### **2. Results**

#### **Data Preprocessing**

- **Target Variable**:  
   - The target variable for the model was `IS_SUCCESSFUL`, which indicates whether a funding application was successful (1) or not (0).

- **Features**:
   - The main features used for this model include:
     - **ASK_AMT**: The requested funding amount.
     - **APPLICATION_TYPE** and **CLASSIFICATION**: Representing the type of application and funding classification, which were one-hot encoded after reducing the number of unique categories.
   - These features were selected for their potential influence on application success.

- **Removed Variables**:
   - Variables excluded from the model include:
     - **EIN** and **NAME**: Unique identifiers that do not contribute to predicting application success.
     - **INCOME_AMT**: This variable was removed due to noise, as it did not meaningfully enhance the model’s accuracy.

#### **Compiling, Training, and Evaluating the Model**

- **Neural Network Structure**:
   - **Neurons**:
     - The first hidden layer was optimized to have **37 neurons**.
     - Additional hidden layers had between 7 and 49 neurons, as determined by the best hyperparameters.
   - **Layers**:
     - The neural network now has **8 hidden layers**, identified as optimal during hyperparameter tuning.
   - **Activation Function**:
     - The **tanh** activation function was selected for the hidden layers, as it yielded better results during tuning compared to ReLU and sigmoid functions.

- **Model Performance**:
   - The final model achieved an accuracy of **74.83%** with a loss of **0.5406** on the test set. This meets the desired target of approximately 75% accuracy, indicating that the model can moderately predict application success.

- **Steps Taken to Improve Performance**:
   - **Hyperparameter Tuning**: The `kerastuner` library's Hyperband search method was used to test various neuron counts, layer structures, and activation functions to optimize model accuracy.
   - **Outlier Removal**: Outliers in the `ASK_AMT` feature were removed using the Interquartile Range (IQR) to minimize data skew.
   - **One-Hot Encoding**: Categorical data, including application types and classifications, were standardized by reducing the number of unique categories and converting them to one-hot encoded columns.

### **3. Summary**

This neural network model for Alphabet Soup achieved an accuracy of **74.83%** on the test set, almost meeting the target of 75%. While this model provides a reasonable level of predictive accuracy, further improvements could enhance its capabilities.

**Recommendation**: To increase accuracy further, we could explore models like Random Forest. It is said that these models tend to perform well on structured data and could help reduce overfitting by combining decision trees, capturing complex patterns in the data.