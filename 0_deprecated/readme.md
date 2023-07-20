# **Data Science CrossFit Project**
This project aims to analyze CrossFit athletes' performance in major competitions over the last three years and develop a model to predict the results of the 2023 CrossFit Games.

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
Data was scraped from the official CrossFit Games website (https://games.crossfit.com/) to gather information about athletes and their performance in official competitions, including the Open, Quarterfinals, Semifinals, and Games, spanning the years 2021 to 2023. The data was acquired through API requests to the CrossFit Games API, utilizing specific endpoints and parameters for each year, competition, and gender. The received JSON responses were processed to extract relevant fields, which were then consolidated into two dataframes per year and competition. One dataframe contains athletes' information, overall score, and rank, while the other dataframe contains athletes' scores and rank per workout.

### **Data Cleaning**
The data cleaning process involved several steps to prepare the data for analysis. Relevant columns were selected from each dataframe and categorized as numeric or categorical variables. Missing values were carefully analyzed and appropriate handling methods, such as removal or manipulation, were applied. Additionally, efforts were made to ensure data consistency by addressing inconsistencies, standardizing formats, and resolving discrepancies across different data sources. Furthermore, new columns were created to record the year and competition for each data entry.

### **Exploratory Data Analysis**
The exploratory data analysis (EDA) was conducted in two steps. In the first step, athletes' information datasets were analyzed by combining them and employing various techniques for comprehensive data analysis. Descriptive statistics, including mean, median, and standard deviation, were computed. A heatmap was generated to understand the correlation between numeric variables. Histograms were created to visualize the distributions of key numeric variables, such as age, height, and weight. Additionally, bar charts were used to extract insights from categorical variables, including gender and region. The second step involves analyzing the athletes' scores datasets, examining the performance workout by workout. This analysis will provide a closer look at the progression and patterns in the athletes' scores over time.

### **Feature Engineering**
Some feature engineering was performed on the dataset prior to model building. Unnecessary columns were dropped, and a new column representing the Body Mass Index (BMI) was created from weight and height measurements. Athletes who participated in the competition games were filtered, and scores and ranks from other competitions were pivoted into new columns for integration. Categorical variables were transformed into numeric variables, and null values were handled individually. Finally, a thorough analysis of the correlation between overall scores and the other variables was conducted.

### **Model Building**
The model was built using data from 2021 and 2022, with the dataset divided into 80% for training and 20% for testing. The data from 2023 was excluded to serve as the target for predictions, allowing for comparison with the actual scores and rankings in the upcoming month. The column 'overallRank' was also excluded as it is directly related to the predicted column 'overallScore', and I won't have one without the other. With a dataset of only 160 rows and 16 columns available for predictions, simple models such as Decision Tree Regressor, Random Forest Regressor, and XGB Regressor were tested. The Decision Tree model performed the worst, while XGB showed better results but still fell short compared to Random Forest. It is important to note that all models presented high mean absolute errors, which can be attributed to the limited amount of information available.

## **Results**
The models' errors were unsatisfactory, with mean absolute percentage errors ranging from 50-70% (equivalent to mean absolute errors of 180-280). As mentioned earlier, these high errors were anticipated due to the limited amount of data available. Despite the challenges, the project provided valuable learning opportunities, particularly in the areas of data scraping, data cleaning, and data analysis. Although I was aware that creating a robust model would be difficult with the limited data, I persevered to explore the possibilities. The experience has provided insights into areas for improvement, including the need to gather more data through data scraping and repeating all steps. In future versions of this project, I will apply these learnings to develop better models.