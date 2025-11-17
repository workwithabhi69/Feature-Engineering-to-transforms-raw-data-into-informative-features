Dataset
This project uses the Heart Disease Dataset from Kaggle, containing patient health metrics such as age, cholesterol, blood pressure, maximum heart rate, and a binary target indicating presence/absence of heart disease.

Feature Engineering Steps Performed
1. Data Loading & Initial Exploration
Loaded the dataset in Google Colab using Pandas.

Checked dataset shape, column types, basic statistics.

Identified presence of categorical and numerical features.

3. Handling Missing Values

Verified missing values using:

df.isnull().sum()

The dataset contained a few missing values, which were handled using mean imputation for numerical features and mode imputation for categorical features.

This ensures consistency and prevents dropping valuable data.

3. Encoding Categorical Variables
   
Columns such as cp, restecg, slope, thal, and ca were converted into numeric format.

One-Hot Encoding was used for multi-category columns to avoid ordinal misinterpretation.

Label Encoding was used only where categorical values represented natural order.

5. Feature Scaling
   
Applied Standardization (Z-score scaling) on numerical columns such as:

age

trestbps

chol

thalach

oldpeak

Scaling was necessary because features were on different units and ranges, which affects distance-based models and gradient-based methods.

7. Dimensionality Reduction (PCA)
   
Applied Principal Component Analysis (PCA) with components explaining ~95% variance.

PCA helped reduce redundant information while maintaining most of the dataset’s variance.

This improves training speed and can reduce overfitting.

9. Feature Selection
    
Performed correlation analysis to understand relationships between features.

Removed features with:

Very low variance

High correlation (>0.85) to avoid multicollinearity

Additional selection using SelectKBest (f_classif) to keep top informative features.

Summary of Impact

Dataset became cleaner and more uniform after scaling and encoding.

PCA reduced dimensionality and revealed hidden structure.

Selected features contributed more strongly to predicting heart disease.

Overall, the preprocessing improved model interpretability and performance.

Summary of Impact

Dataset became cleaner and more uniform after scaling and encoding.

PCA reduced dimensionality and revealed hidden structure.

Selected features contributed more strongly to predicting heart disease.

Overall, the preprocessing improved model interpretability and performance.
