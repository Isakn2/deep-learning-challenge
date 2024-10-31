# Alphabet Soup Charity Funding Predictor

This project aims to predict the success of funding applications for the fictional charity "Alphabet Soup" using a deep learning model. By analyzing previous application data, this model can support data-driven funding decisions, improving charity's operations.

## Project Overview

- **Goal**: Develop a neural network model to classify the likelihood of funding success.
- **Data Source**: [Charity Data CSV](https://static.bc-edx.com/data/dl-1-2/m21/lms/starter/charity_data.csv)

## Key Steps

1. **Data Preprocessing**:
   - Target: `IS_SUCCESSFUL` column.
   - Features: `ASK_AMT`, `APPLICATION_TYPE`, `CLASSIFICATION`, and other structured data.
   - One-hot encoding and outlier removal were applied for optimal model input.

2. **Model Development**:
   - A Sequential neural network was optimized using KerasTuner.
   - Hyperparameter tuning determined the optimal neuron count, layers, and activation functions.
   - Best model achieved **74.83% accuracy** with minimized loss.

3. **Results & Recommendations**:
   - The model successfully meets performance targets.
   - Suggestions include exploring ensemble models for potential accuracy improvements.

## Usage

- **Export Model**: The final model is saved as an HDF5 file in the `Output_model` directory.
- **Dependencies**: Install required libraries using `requirements.txt`.


## Technologies

- **Python** (Pandas, NumPy, Scikit-Learn)
- **TensorFlow/Keras** (for model training)
- **KerasTuner** (for hyperparameter optimization)