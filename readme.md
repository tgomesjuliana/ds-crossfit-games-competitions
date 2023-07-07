# **Data Science CrossFit Project**
This is my first data science project, aiming to cover all steps involved in a data science project, from data collection to model productionization. The goal is to compare CrossFit athletes' performance in the most important competitions over the last three years to gain a deeper understanding of the subject. Additionally, I plan to create a model to predict the results of this year's most important competition.

## **Project Steps**
1. **Data Collection**: Scrape data from the official CrossFit Games website.
2. **Data Cleaning**: Filter relevant columns and handle missing values.
3. **Exploratory Data Analysis**: Analyze variables statistically to gain insights.
4. **Feature Engineering**: Create new columns with relevant data to enhance the model.
5. **Model Building**: Develop, compare, and fine-tune machine learning models.
6. **Model Productionization**: Deploy the model for production use.

### **Data Collection**
Data was scraped from the official CrossFit Games website (https://games.crossfit.com/) to gather information about athletes and their performance in the official competitions, including the Open, Quarterfinals, Semifinals, and Games, covering the years 2021 to 2023. It was obtained by making API requests to the CrossFit Games API, utilizing specific endpoints and parameters for each year, competition, and gender. The JSON responses received were processed to extract relevant fields (athlete's rank, informations and scores).

### **Data Cleaning**
The data cleaning process involved selecting relevant columns within each dataframe and categorizing them as numeric (float) or continuous (object) variables. Missing values were analyzed for each column to determine the impact and appropriate handling method. Also, some columns required minor treatment to ensure data consistency and new columns were created to record the year and the competition for each data entry.

### **Exploratory Data Analysis**
The exploratory data analysis began by combining all athletes' information datasets (by year and competition) into one. Further data cleaning and feature engineering were performed, including the transformation of height and weight into numeric variables of the same measure unit (cm and kg). Histograms were created for the most important numeric variables, such as age, height, and weight. Ongoing analysis focuses on continuous variables.

### **Feature Engineering**
WIP

### **Model Building**
WIP

### **Model Productionization**
WIP

## **Lessons Learned**
1. **Project Ideation**:
* Have it clear what's the variable you want to predict since the start
* Check if you have enough data available to create a trustable prediction
2. **Use of ChatGPT**:
* Checking and correcting queries
* Adding comments on what's being done
* Improving queries performance
* Factorizing queries into functions