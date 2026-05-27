# Specialized Data Science Program - Universidad de los Andes

This repository contains the data science exercises developed as part of the Specialized Data Science Program at Universidad de los Andes.

## Course 3: Data Integration and Preparation
This course covers data integration from multiple sources and essential preparation techniques aligned with ASUM-DM. Topics include data profiling, type validation, consistency checks, duplicate handling, fuzzy matching, feature engineering (normalization, transformation, PCA, scaling), and text processing with spaCy (tokenization). The focus is on preparing reliable, high-quality data for downstream analytics.

#### [Employee Turnover](integration_and_preparation.ipynb)
Performs data preparation, exploratory data analysis (EDA), feature transformation, standardization, and Principal Component Analysis (PCA) on an employee dataset to evaluate the feasibility of dimensionality reduction for employee turnover prediction.

Key Tasks:

- Data profiling (identifying data types, missing values, duplicates, and basic statistics)
- Data consistency: comparing values in the dataset with the data dictionary, correcting spelling errors, and validating categorical matches
- Variable transformation
- Feature engineering
- Standardization: applying StandardScaler to normalize numerical attributes
- Dimension reduction using PCA

Tools used: Pandas, YData Profiling, Scikit-learn (StandardScaler, PCA), Matplotlib

**Note:** The command for generating the report with YData Profiling is commented out to reduce the file size

#### [Exercise 1: Working with different types of files](Load_data.ipynb)
Loads and compares three data files in different formats (CSV, Excel, JSON) to identify structural differences, data types, and content patterns.

Key Insights:
- CSV and Excel Sheet 2 are equivalent (same dimensions and patterns)
- Excel Sheet 1 is smaller (100 rows) with unnamed columns
- JSON is a minimal dataset (10 rows, 10 columns)

Tools used: Pandas, OS, JSON

#### [Exercise 2: Data Integration with Merge and Join](join.ipynb)

Demonstrates the difference between `merge()` and `join()` for data integration in pandas:

- `merge()`: SQL-style joins based on columns (relational). Ideal when DataFrames share a key column.
- `join()`: Index-based joining. Simpler syntax for combining DataFrames by their indices.

Tools used: Pandas (merge, join)

#### [Exercise 3: Principal Component Analysis](PCA.ipynb)
Applies Principal Component Analysis (PCA) to an employee dataset in order to reduce dimensionality and identify the variables that contribute most to employee turnover.

Key Tasks:

- Data preprocessing and cleaning (handling missing values, duplicate records, and categorical encoding)
- Feature standardization using StandardScaler
- Dimensionality reduction with PCA
- Analysis of explained variance and principal components

Tools used: Pandas, Scikit-learn (StandardScaler, PCA), Matplotlib

#### [Exercise 4: spaCy transformations](spacy.ipynb)
Analyzes hotel review descriptions using spaCy for Spanish to compare semantic similarity between different hotel descriptions.

Key Tasks:

- Load Spanish language model (`es_core_news_md`)
- Process hotel descriptions with spaCy (tokenization, lemmatization, POS tagging)
- Calculate semantic similarity between hotel descriptions using word vectors

Tools used: spaCy, Pandas

**Note:** This notebook is an adaptation of the original from Universidad de los Andes, created to demonstrate text transformation skills not covered in the main course project.

## Course 2: Predictive models using machine learning
This course focuses on data analysis and machine learning. It covers supervised and unsupervised models, as well as the development of predictive regression and classification models. It also addresses model evaluation and the management of parameters and hyperparameters, following the comprehensive process of creating data-driven solutions, from problem definition to interpretation.

### Classification models

#### [Water Quality Prediction - Decision Tree](Water_Quality_Classification_Model.ipynb)
Predicts water suitability for human consumption using a Decision Tree classifier based on physicochemical parameters. Hyperparameter tuning performed with GridSearchCV (criterion: gini/entropy, max_depth: 4-12, min_samples_split: 3-5) with class_weight='balanced'.

Key Results:

| Metric | Value |
|--------|-------|
| Best Parameters | criterion='gini', max_depth=10, min_samples_split=4 |
| Accuracy | 59% |
| Recall (YES - suitable) | 61% |
| Precision (NO - unsuitable) | 71% |

Key Insights:
- pH and sulfates are the dominant predictors of water quality
- Recall is the most critical metric (identifying safe water for consumption)
- Model performance is moderate (59% accuracy) and could be improved with more data or ensemble methods

Tools used: Pandas, Scikit-learn (DecisionTreeClassifier, GridSearchCV), Matplotlib, Seaborn, YData Profiling

#### [Exercise 1: Cardiovascular Disease Prediction - Decision Tree](Decision_tree_Cardiovascular_diseases.ipynb)
Predicts cardiovascular disease (CVD) risk using a Decision Tree classifier with clinical and lifestyle patient data.

Key Results:

- Accuracy: 64%
- True Positives (CVD detected): 4,151
- False Negatives (CVD missed): 2,577

Key Insights:
- Age and weight together account for 45.1% of predictive importance
- Lifestyle factors (smoking, alcohol, physical activity) showed minimal influence

Tools used: Pandas, Scikit-learn (DecisionTreeClassifier), Matplotlib, ydata_profiling

#### [Exercise 2: Cardiovascular Disease Prediction - Decision Tree with Hyperparameter Tuning](Decision_tree_Hyperparameter_tuning.ipynb)
Compares default vs tuned Decision Tree classifiers for cardiovascular disease (CVD) risk prediction using clinical and lifestyle patient data. Hyperparameter tuning performed with GridSearchCV (criterion: gini/entropy, max_depth: 4-10, min_samples_split: 2-5).

Key Results:

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Default | 63.7% | 63.8% | 61.7% | 62.7% |
| Tuned | 73.0% | 75.7% | 67.0% | 71.1% |

Key Insights:
- Hyperparameter tuning improved accuracy by +9.3%
- Tuned model identified **systolic blood pressure** as dominant predictor (73.3% importance)
- Anthropometric variables (weight, height) lost relevance after tuning
- Lifestyle factors showed minimal influence across both models

Tools used: Pandas, Scikit-learn (DecisionTreeClassifier), Matplotlib, ydata_profiling

### Predictive models

#### [Regression model: Forest Fire Burned Area](Regression_model_wildfires.ipynb)
Predicts burned area using Linear, Ridge, Lasso, and Polynomial (degree 2) regression. Hyperparameter tuning via GridSearchCV (Ridge α=[0.1,0.5,1.0], Lasso α=[1,2,3,4,5]) and validation set for polynomial degree selection.

Key Results:

- Best model: Polynomial (degree 2) – R² = 0.235, RMSE = 17,184, MAE = 3499.11
- Ridge α = 1.0, Lasso α = 5
- Lasso eliminated 5 features and the most important predictor was clase_incendio_G (coefficient +8,141)

Tools used: Pandas, NumPy, Scikit-learn (LinearRegression, Ridge, Lasso, PolynomialFeatures, Pipeline, GridSearchCV), Matplotlib, Statsmodels, ydata_profiling

#### [Exercise 1: Real State Sells](Real_state_1.ipynb)
This exercise performs exploratory data analysis (EDA) on real estate data, analyzing variables such as bedrooms, bathrooms, area, and condition to understand their influence on housing prices.

The analysis includes automated data profiling, descriptive statistics, and visual exploration of correlations with price.

Tools used: Pandas, Matplotlib, Seaborn, YData Profiling

#### [Exercise 2: Real State Sells](Real_state_2.ipynb)
This project uses a linear regression model to predict home prices. The process includes data preparation, model building, evaluation, and statistical interpretation.

Key Results:
- R² = 0.90 (model explains 90% of price variability)
- Model is statistically significant (F-statistic = 5470, p = 0.00)
- Strongest predictors: `grado` (+$75,810), `numero_pisos` (+$43,130), `condición` (+$25,380)
- Severe multicollinearity detected (Condition Number = 148,000)

Conclusions:
The model has excellent predictive power but multicollinearity distorts individual coefficient interpretations. Useful for predictions, but caution needed when interpreting isolated variable effects.

Tools used: Pandas, NumPy, Scikit-learn, Statsmodels

#### [Exercise 3: Real State Polynomial vs Linear Regression](Real_state_3.ipynb)

This notebook compares the performance of a second-degree polynomial regression model against a standard linear regression model to predict property prices.

Tools used: Pandas, Scikit-learn (LinearRegression, PolynomialFeatures, train_test_split, metrics), Matplotlib

Methodology: Aligned with ASUM-DM (IBM) phases: Business Understanding → Data Preparation → Model Building → Evaluation

#### [Exercise 4: Real State Regularized Regression (Ridge & Lasso)](Real_state_4.ipynb)

Predicts property prices using Ridge and Lasso regression with hyperparameter tuning (α = [0.1, 0.25, 0.5]) via GridSearchCV.

Key insights:
- No features eliminated by Lasso (all 9 contribute)
- Most important feature: `grado` (+82,318)

Tools: Pandas, Scikit-learn (Ridge, Lasso, Pipeline, GridSearchCV), Matplotlib

Methodology: ASUM-DM

## Course 1: Introduction to data science
The exercises for the first course were conducted using an Airbnb dataset containing information on rental listings in Amsterdam. The original dataset is publicly available at https://insideairbnb.com/get-the-data/, though the version used in this course was modified for academic purposes.

### Exercises
#### [Exercise 1: Airbnb Amsterdam](Airbnb_1.ipynb)
This exercise test four statistical hypotheses about rental listings. Using descriptive statistics and data analysis techniques such as percentiles, measures of central tendency, and standard deviation, the following hypotheses were evaluated:

1. 53% of review scores fall between 20 and 96 points. 
2. The average rental price above the 78th percentile is 300 euros. 
3. 20% of properties are rented below the city average price. 
4. Alberto claims to have rented a property for 130 euros, one standard deviation above the average. 

Tools used: Pandas, NumPy, Matplotlib, Plotly

#### [Exercise 2: Airbnb Amsterdam](Airbnb_2.ipynb)
This exercise tests five statistical hypotheses about rental listings. Using descriptive statistics and data analysis techniques such as frequency tables, percentiles, measures of central tendency, and measures of variation the following hypotheses were evaluated:

1. 50% of the listings on the platform primarily offer hotel rooms.
2. The vast majority of private rooms are priced between 4 and 129 euros. 
3. Houses and apartments have the highest review ratings on the platform. 
4. Houses and apartments have the widest range of rental prices.
5. The listings with the best price scores are houses, apartments, and hotel rooms.

Tools used: Pandas, NumPy, Plotly

#### [Exercise 3: Airbnb Amsterdam](Airbnb_3.ipynb)
In this study, visualization techniques and correlation coefficient calculations (Pearson and Spearman) were used to analyze the relationship between variables and evaluate the hypotheses regarding direct and inverse proportionality.
The hypotheses to be tested are:

1. Review scores and communication scores are directly proportional.
2. The relationship between rental price and the number of rooms is inversely proportional.

Tools used: Pandas, NumPy, Plotly

#### [Exercise 4: Airbnb Amsterdam](Airbnb_4.ipynb)
This exercise tests three statistical hypotheses regarding rental listings. Using descriptive statistics and data analysis techniques, such as frequency tables, percentiles, and filtering, the following hypotheses were evaluated:

1. If a property with a review score between 80 and 89 points is listed, 80% of the listings are likely to be private rooms, houses, or apartments.
2. If a house or apartment is rented, 30% of the listings will have a review score between 80 and 100 points.
3. 30% of the listings are private rooms with review scores between 90 and 100 points.

Tools used: Pandas, NumPy, Matplotlib, Plotly

#### [Exercise 5: Airbnb Amsterdam](Airbnb_5.ipynb)

The objective of this exercise was to construct a confidence interval for real estate prices, perform hypothesis testing, and conduct a p-test to compare samples of two-bedroom apartments located in the Centrum-Oost and Centrum-West neighborhoods, in order to determine whether or not there is a difference in prices between these two neighborhoods.

Tools used: Pandas, NumPy, Statsmodels.stats

#### [Exercise 6: Airbnb Amsterdam](Airbnb_6.ipynb)
In this study, a one-way analysis of variance (ANOVA) was conducted to assess whether there are significant differences in property prices based on the type of accommodation (room_type) in the central area of Amsterdam (Centrum-Oost and Centrum-West).

Tools used: Pandas, NumPy, scipy.stats, Matplotlib, seaborn
