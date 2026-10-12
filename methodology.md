Methodology

1. Refined Research Question
How do the physical, chemical, structural, and magnetic properties of magnetic nanoparticles influence their specific absorption rate (SAR), and which machine learning models can best predict SAR to identify promising candidates for effective magnetic hyperthermia applications?

The main objective of this study is to use published experimental data to investigate the relationships between nanoparticle properties and SAR. The study will compare different machine learning models to identify promising nanoparticles for magnetic hyperthermia applications.

2. Dataset Description

Data Sources:
Experimental data will be collected from published research articles and publicly available repositories. The initial sources include:

https://doi.org/10.1002/cphc.202400023
https://doi.org/10.17044/SCILIFELAB.29835419
https://doi.org/10.5281/zenodo.7596848

The available data will be extracted, combined, and organized into a structured dataset for machine learning.

Features:
The input features will include available physical, chemical, structural, and magnetic properties of the nanoparticles. Depending on data availability, these may include:
a. Physical properties, such as particle size and shape.
b. Chemical properties, such as chemical composition and coating materials.
c. Structural properties, such as crystal structure.
d. Magnetic properties, such as saturation magnetization and coercivity.
e. Experimental conditions, such as magnetic field strength and frequency, when available.

The final feature list will depend on the variables reported consistently across the collected sources.


Target Variable:
The target variable will be the specific absorption rate (SAR). It represents the rate at which magnetic nanoparticles dissipate energy as heat under specified conditions.
SAR will be treated as a continuous numerical variable; therefore, the primary task will be a regression problem.

Dataset Size and Limitations:
The final dataset size will be determined after data collection and cleaning. The number of samples, number of features, and amount of missing data will be reported after the dataset has been compiled.

Potential limitations include:
Limited availability of experimental data.
Missing or inconsistently reported features.
Differences in measurement methods and experimental conditions across publications.
Variations in units and reporting standards.
A potentially small dataset.
Differences in SAR values caused by experimental conditions rather than nanoparticle properties alone.

These limitations will be considered during preprocessing, model development, and interpretation of the results.

3. Data Cleaning and Preprocessing:
a. Data integration: Combine data from the selected publications and repositories into a single structured dataset.
b. Duplicate removal: Identify and remove duplicate records while retaining relevant experimental observations.
c. Data type checking: Ensure that numerical and categorical variables are represented appropriately.
d. Unit standardization: Convert measurements to consistent units wherever possible.
e. Missing-value handling: Examine the extent and patterns of missing values. Numerical features may be imputed using the median or mean, while categorical features may be imputed using the most frequent category when appropriate. 
f. Data splitting: Divide the dataset into training and test sets. Preprocessing parameters will be learned from the training data only to avoid data leakage.
g. Because the data will be collected from multiple publications, the possibility of overlapping samples or repeated measurements will also be investigated.


4. Feature Engineering:
a. Selecting relevant features based on scientific knowledge and data availability.
b. Encoding categorical variables, such as particle shape, coating type, and chemical composition, into numerical representations where necessary.
c. Examining correlations between input features to identify potentially unnecessery variables.
d. Investigating whether experimental conditions, such as magnetic field strength and frequency, should be included to improve SAR prediction.
e. Considering transformations of highly skewed numerical variables if justified by exploratory data analysis.
f. Missing-value imputation and feature scaling will be performed as preprocessing steps within the modeling pipeline.
g. Min–Max scaling will be applied to numerical features for Support Vector Regression and Ridge Regression when appropriate. Random Forest regression does not generally require feature scaling.
h. Missing values will not be filled using the previous observation unless the data have a meaningful sequential or grouped structure that justifies this approach.


5. Machine Learning Models:
a. Support Vector Regression (SVR): it can model nonlinear relationships through the use of appropriate kernels. It can be useful for small or medium-sized datasets, although its performance depends on feature scaling and hyperparameter selection.

b. Ridge Regression: Its a regression model that helps reduce overfitting. It provides a useful baseline and can perform well when features are correlated or when the number of features is relatively large compared with the number of samples. However, it may not suitable for complex nonlinear relationships without additional feature transformations.

c. Random Forest Regression: it is an ensemble learning method that combines multiple decision trees. It can work on nonlinear relationships and interactions between features and generally does not require feature scaling. However, its performance may be limited by a very small dataset, noisy observations, or substantial differences between experimental sources.

(............more models will be used.........)

Model Selection and Comparison:
All three models will be trained using the same training data and evaluated using the same test set. Hyperparameter tuning will be performed using cross-validation on the training data, where the dataset size permits.

The final model will be selected based on its predictive performance and its ability to generalize to unseen data.

6. Evaluation Metrics:
a. Mean Absolute Error (MAE): erroe
b. Root Mean Squared Error (RMSE): error
c. Coefficient of Determination (R²): complementary measure of model fit

