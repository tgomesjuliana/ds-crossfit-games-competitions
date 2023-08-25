# **Data Science CrossFit Games Competitions Project**
This project aims to analyze CrossFit athletes' performance between the first and last competitions over the last seventeen years and develop a model to predict the results of the 2023 CrossFit Games.

## **Table of Contents**
- [Resources](#resources)
- [Steps](#steps)
  - [Summary](#summary)
  - [Data Collection](#data-collection)
  - [Data Cleaning](#data-cleaning)
  - [Exploratory Data Analysis](#exploratory-data-analysis)
  - [Feature Engineering](#feature-engineering)
  - [Model Building](#model-building)
- [Results](#results)
- [Lessons Learned](#lessons-learned)

## **Resources**
Code Editor: Visual Studio Code and Kaggle.
Python Version: Python 3.11 inside Visual Studio Code and 3.7 inside Kaggle.
Python Packages: requests, pandas, os, numpy, math, plotly, seaborn, matplotlib, sklearn, xgboost.

## **Steps**

### **Summary**
1. **Data Collection**: Scrape data from the official CrossFit Games website.
2. **Data Cleaning**: Filter relevant columns and handle missing values.
3. **Exploratory Data Analysis**: Analyze variables statistically to gain insights.
4. **Feature Engineering**: Create new columns with relevant data to enhance the model.
5. **Model Building**: Develop, compare, and fine-tune machine learning models.

### **Data Collection**
Data was scraped from the official CrossFit Games website (https://games.crossfit.com/) to gather information about athletes and their performance in the Crossfit Games, covering the years 2007 to 2023, and in the Crossfit Open, covering the years 2011 to 2023. Data was obtained by making API requests to the CrossFit Games API, utilizing specific endpoints and parameters for each year, competition, and gender. The JSON responses received were processed to extract relevant fields (athlete's information, scores, and ranks).

### **Data Cleaning**
Data was subjected to a comprehensive process to prepare it for further analysis. To address inconsistencies, country and region were carefully handled, and, together with the status column, a numeric representation was created for each. Height and weight were standardized each to a common unit, leading also to the creation of a Body Mass Index (BMI) column. Games overall score and rank were processed to remove strings and handle missing data. Missing information for age, height, weight, BMI, and affiliate columns was individually addressed. Furthermore, a new column indicating the number of games competitions an athlete had participated in was introduced. Finally, information from the Open, including overall score, rank, and number of open competitions, was also incorporated into the dataset. Columns were re-ordered to enhance data organization before exporting the dataset to a single file. This data cleaning and feature engineering process resulted in an enriched dataset, ready for deeper insights into CrossFit athletes' performance in the competitions.

### **Data Analysis**
Data was analyzed in several steps to extract valuable insights. Initially, a heatmap was generated to explore correlations between numeric variables, with a particular focus on the Games' overall score. While some correlations, such as rank, number of competitions, and Open information, were expected, not so clear correlations emerged, especially with region and country. To further investigate attributes, histograms were plotted for most numeric variables, and, specifically for height, weight, and BMI, a split by gender was created for a more comprehensive analysis. Additionally, histograms were used to compare these variables with the average Games' overall score and rank, allowing a deeper understanding of their relations, revealing potential patterns and trends. For categorical variables, bar charts were plotted to also examine their distribution and comparison with the average Games' overall score and rank. Particularly interesting insights were extracted from the analysis of regions: it became evident that North America dominates the number of athletes, followed by Europe with roughly a third of that number, and Oceania with around seven times fewer athletes. Despite the disparity in athlete numbers, these three regions exhibited similar Games' overall scores and ranks, while regions such as South and Central America, Africa, and Asia lagged behind the dominant regions in terms of performance. Overall, this data analysis provided meaningful findings, shedding light on the relationships between various factors across CrossFit athletes' performance in the competitions.

### **Feature Engineering**
All new features were already created, missing data was handled, and categorical variables were transformed into numeric during the data cleaning phase, so this phase didn't add, remove, or transform any columns. Instead, the mutual information function from scikit-learn (sklearn) was used to quantify the amount of information one variable provides about another variable, with the variable under study being the Games' overall score. As mentioned earlier, the most dependent variables here were Games' overall rank, followed by region, country, number of Games competitions, and Open's overall rank. After that, scatter plots were plotted for most numeric variables to visualize their relations, and regplots were used to show the best-fitting line representing the linear relationship between the two variables.

### **Model Building**
Model was built excluding the year 2023 and the column Games' overall rank as it depends on the score, also, the dataset was divided into 80% training and 20% testing. The first models built were linear regression and lasso regression, both with a mean absolute error (MAE) around 150. After that, nonlinear regressions were used, including decision trees, which achieved MAEs ranging from 120 to 140 depending on the parameters chosen, and random forests which consistently yielded better results, with MAEs around 100 for various parameter combinations. A XGBoost (XGB) model was also created, resulting in MAEs ranging from 100 to 120 based on the selected parameters. Overall, the results demonstrate significant improvement compared to the initial attempt of the project, where MAEs ranged from 180 to 280.

## **Results**
In this second attempt, the models' performance showed significant improvement, with mean absolute errors (MAEs) ranging from 100 to 150, compared to 180 to 280 in the initial try of the project. These lower errors can be attributed to several factors, including the increased amount of data scraped (1600 rows compared to 160 rows before), more meticulous data cleaning, and the introduction of new engineered features. Despite encountering various challenges, curiosity and determination drove the project forward, resulting in valuable insights not only about CrossFit competitions but also about data science and machine learning models.

## **Lessons Learned**
1. **Data Quality**: To achieve reliable predictions, have clear goals and ensure data available is enough. Handle missing or inconsistent data to prevent bias and errors, ensuring data accuracy and completeness.
2. **Iterative Approach**: Data cleaning, analysis, and feature engineering are interconnected processes that may require iterative adjustments based on new insights. Continuously improve the model for better results.
3. **Domain Knowledge**: Leverage domain knowledge to guide all steps, from data cleaning to model building. Understand the context and nuances of the data to identify relevant old features or meaningful new features.
4. **Model Validation**: Validate the model on unseen data by splitting the data or using techniques like cross-validation. This helps assess the model's generalization capabilities and prevents overfitting.
5. **Factorizing Functions**: Be cautious about investing excessive time in factorizing queries into optimized and replicable functions, as project approaches may change rapidly, leading to potential rework on coding.
6. **Use of ChatGPT**: Maximize efficiency with ChatGPT. Check, correct, factorize, and improve queries, add comments to improve readiness, implement error-checking to facilitate debugging, and create insightful charts.
7. **Reproducibility**: Ensure reproducibility with well-documented steps, organized code, and version control, allowing collaboration with other data scientists for future verification or replication.
8. **Continuous Learning**: Embrace continuous learning in data science. Stay updated with the latest tools, techniques, and best practices through online courses, and active engagement in data science communities.

Overall, this project showcases the potential of data science in exploring athletic performance and offers valuable insights for future analysis and modeling.
