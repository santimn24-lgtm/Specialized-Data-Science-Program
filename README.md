# Specialized Data Science Program - Universidad de los Andes

This repository contains the data science exercises developed as part of the Specialized Data Science Program at Universidad de los Andes.

## Course 2: Predictive models using machine learning
This course focuses on data analysis and machine learning. It covers supervised and unsupervised models, as well as the development of predictive regression and classification models. It also addresses model evaluation and the management of parameters and hyperparameters, following the comprehensive process of creating data-driven solutions, from problem definition to interpretation.

### Exercises
#### [Exercise 1: Real State Sells](Real_state_1.ipynb)
This exercise performs exploratory data analysis (EDA) on real estate data, analyzing variables such as bedrooms, bathrooms, area, and condition to understand their influence on housing prices.

The analysis includes automated data profiling, descriptive statistics, and visual exploration of correlations with price.

**Tools used:** Pandas, Matplotlib, Seaborn, YData Profiling

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
