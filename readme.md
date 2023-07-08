# **Data Science CrossFit Project**

[TOC]

## **Table of Contents**
- [Description](#description)
- [Resources](#resources)
- [Steps](#steps)
  - [Summary](#summary)
  - [Data Collection](#data-collection)
  - [Data Cleaning](#data-cleaning)
  - [Exploratory Data Analysis](#exploratory-data-analysis)
  - [Feature Engineering](#feature-engineering)
  - [Model Building](#model-building)
  - [Model Productionization](#model-productionization)
- [Results](#results)
- [Lessons Learned](#lessons-learned)

## **Description**
This project aims to analyze CrossFit athletes' performance in major competitions over the last three years and develop a model to predict the results of the 2023 CrossFit Games.

## **Resources**
Code Editor: Visual Studio Code and Kaggle.  
Python Version: Python 3.11 inside Visual Studio Code and 3.7 inside Kaggle.  
Python Packages: requests, pandas, os, numpy, math, plotly.

## **Steps**

### **Summary**
1. **Data Collection**: Scrape data from the official CrossFit Games website.
2. **Data Cleaning**: Filter relevant columns and handle missing values.
3. **Exploratory Data Analysis**: Analyze variables statistically to gain insights.
4. **Feature Engineering**: Create new columns with relevant data to enhance the model.
5. **Model Building**: Develop, compare, and fine-tune machine learning models.
6. **Model Productionization**: Deploy the model for production use.

### **Data Collection**
Data was scraped from the official CrossFit Games website (https://games.crossfit.com/) to gather information about athletes and their performance in official competitions, including the Open, Quarterfinals, Semifinals, and Games, spanning the years 2021 to 2023. The data was acquired through API requests to the CrossFit Games API, utilizing specific endpoints and parameters for each year, competition, and gender. The received JSON responses were processed to extract relevant fields, which were then consolidated into two dataframes per year and competition. One dataframe contains athletes' information, overall score, and rank, while the other dataframe contains athletes' scores and rank per workout.

### **Data Cleaning**
The data cleaning process involved several steps to prepare the data for analysis. Relevant columns were selected from each dataframe and categorized as numeric or categorical variables. Missing values were carefully analyzed and appropriate handling methods, such as removal or manipulation, were applied. Additionally, efforts were made to ensure data consistency by addressing inconsistencies, standardizing formats, and resolving discrepancies across different data sources. Furthermore, new columns were created to record the year and competition for each data entry.

### **Exploratory Data Analysis**
The exploratory data analysis (EDA) was conducted in two steps. In the first step, athletes' information datasets were analyzed by combining them and employing various techniques for comprehensive data analysis. Descriptive statistics, including mean, median, and standard deviation, were computed. A heatmap was generated to understand the correlation between numeric variables. Histograms were created to visualize the distributions of key numeric variables, such as age, height, and weight. Additionally, bar charts were used to extract insights from categorical variables, including gender and region. The second step involves analyzing the athletes' scores datasets, examining the performance workout by workout. This analysis will provide a closer look at the progression and patterns in the athletes' scores over time.

### **Feature Engineering**
Work in progress.

### **Model Building**
Work in progress.

### **Model Productionization**
Work in progress.

## **Results**
Work in progress.

## **Lessons Learned**
1. **Project Ideation**:
* Have it clear what's the variable you want to predict since the start
* Check if you have enough data available to create a trustable prediction
2. **Use of ChatGPT**:
* Check and correct queries
* Add comments on what's being done
* Improve queries performance
* Factorize queries into functions
* Create checks for errors
* Create or improve charts