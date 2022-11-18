# Machine Learning Model Deployment

## Use Case Summary

### Objective Statement
- Get business insight about how growth visitors and buyers in a month at Supermarket
- Get business insight about each visitors based on label defined such as Wandering Customer, Need-Based Customer and Loyal Customers at Supermarket
- Create modeling using Simple Linear Regression
- Deployment machine learning using MLflow

### Challenges
- It is not known what time and what day this Supermarket operates

### Methodology
- Descriptive Analysis
- Graph Analysis
- Machine learning Simple Linear Regression
- Deployment MLflow

### Business Benefit
- Know how to treat visitors based on their behavior when buy products in Supermarket
- Help the business team provide products or services based on the behavior of each customer

### Expected Outcome
- Know how growth visitors and buyers in a month at Supermarket
- Know each visitors based on label defined such as Wandering Customer, Need-Based Customer and Loyal Customers at Supermarket
- Know how create machine learning model using Linear Regression
- Know how to deploy machine learning using MLflow

## Business Understanding
Supermarket is a place that sells a variety of goods, such as food, drinks to household goods. Every day there are always visitors who come to buy or maybe just look around product that Supermarket display. So from here we get questions about visitors as follows:
- How growth visitors and buyers in a month at Supermarket ?
- How each vistors based on label defined such as Wandering Customer, Need-Based Customer and Loyal Customers at Supermarket ?
- How create machine learning using Linear Regression ?
- How deploy machine learning using MLflow ?

## Data Understanding

### Source Data
The dataset has 2 columns and 30 rows, contains daily total visitors and buyers for a month. We get dataset from this site https://www.kaggle.com/datasets/reyanmatrika/supermarket-visitor-linear-regression

### Data Dictionary
- Visitor : the number of people who visit the supermarket
- Buyer : the number of person who buys something in a supermarket

## Data Preparation
- Programming Language : Python Version 3.9.12
- Library : pandas, numpy, matplotlib, seaborn, statistics, sklearn, warning, urlparse, mflow, logging, os, sys

## Data Profiling
We used **supermarket_visitor.csv** dataset in this project. The **supermarket_visitor.csv** dataset store 2 columns with 30 rows of data. Where is a visitor column store data about the total visitors and a buyer column store data about the total buyers in a supermarket.

## Data Cleansing
**No need to cleaning dataset** because the data types of both two columns are correct and there are no missing value in rows

## Exploratory Data Analysis
**We are comparing the growth between visitor and buyer with line chart.**
![image](https://user-images.githubusercontent.com/50388300/202604992-91648ca9-57c9-4727-a28a-1b98ce5e487d.png)

From the graph it can be seen that the growth of buyers has not changed significantly. But if we see the visitor graph there are in days 12 and 14 the number of visitor reaches the highest number. This probably caused by a event where people just wandering around without make a purchased.

**We are labeling visitors based on their behavior**

![image](https://user-images.githubusercontent.com/50388300/202604261-1c2ad0aa-a11e-42d9-9155-3372533eb956.png)

Within 30 days all visitors in supermarket can be grouped into 3 categories based on their behavior, it is Wandering Customers, Loyal Customers and Need Based Customers. **Wandering Customers** are the type of visitors who only look at the products offered. Then there are **Loyal Customers** are visitors purchase product offered repeatedly. And the last **Need-Based Customers** are visitors who only buy based on what is their needed.

## Preprocessing Model
THere are 2 steps in this preprocessing steps :
- We determine Y column, using Buyer column
- After determine the Y column, we split the dataset to training model and testing model with the proportion of 1/3

## Modeling
**How to create machine learning using Linear Regression ?**
- Modeling Simple linear regression is a regression model that estimates the relationship between one independent variable and one dependent variable using a straight line.
- In this case we will chose a linear regression model to predict y variables which is Buyer. 
- After we predict the result, we plot it in bar chart and scatter plot.
![download](https://user-images.githubusercontent.com/113870155/202477662-a3ccfec2-5e99-47e6-82dc-525c9d67dd85.png) 
- From the bar chart, most of the model prediction value is under the actual value.
![download](https://user-images.githubusercontent.com/113870155/202478089-c0d1f811-4679-4493-8a8d-0da3408d81c5.png)
- From the chart we can see most of the model predicted value is under the actual value. And the increasing number of visitors, the **model prediction less accurately**.

## Evaluate 
We evaluate the model we will use RMSE, MAE, MAPE, and R Square to see the model performance
- **Root Mean Square Error (RMSE)** is used to determine the magnitude of the prediction error rate. Where the smaller (closer to 0) the RMSE value, the more accurate the prediction results will be
- **Mean Absolute Error (MAE)** is used to calculate the magnitude of the difference between predict and result
- **Mean Absolute Percentage Error (MAPE)** is used to calculate the percentage of average absolute error
- **r2** is coefficient of determination which shows how well the model fits the dependent variable
- Based on the evaluation that has been carried out, the results for the **RMSE is 2.9**, which means that the model does not predict accurately. The value of the difference between predict and result **(MAE) is 2.3**, with a **MAPE is 6%** which means the error value is quite low. And the last, for **R-Square with a value of -0.17** which means that between buyers and visitors, it shows that the two have a weak correlation.

## Deployment
**How to deploy machine learning using MLflow ?**
- MLflow Tracking is an API and user interface component that records data about machine learning experiments and lets you query it. MLflow Tracking supports Python, as well as various APIs like REST, Java API, and R API.

## Result
We assumed this dataset contains data visitors and buyer at supermarket within 30 days, the **average visitors** in a supermarket **up to 35 visitors per day**. When the supermarket **not crowded**, there are only about **29 people per day**. But when the **supermarket is crowded**, visitors can reach **up to 42 visitors per day**.
Meanwhile the average of visitors who **make purchases up to 33 visitors**. When supermarket is **crowded, up to 38 people make purchases**. And only **29 visitors** make purchases when supermarket **not crowded**. 

In those 30 days it is known that **94.89% visitors make purchases** in supermarket. Whereas total visitors in supermarket up to 1056 visitors and total visitors make purchases up to 1002 visitors. 

In **22 days** there are supermarket visitors **who only look** at the products offered or called Wandering Customers. For **7 days** there are visitors who **buy more than 1 product** offered or called Loyal Customers. And only **1 day** visitors who actually **buy what they need** or called Need-Based Customers.

Based on the evaluation that has been carried out, the results for the **RMSE is 2.9**, which means that the model does not predict accurately. The value of the difference between predict and result **(MAE) is 2.3**, with a **MAPE is 6%** which means the error value is quite low. And the last, for **R2 with a value of -0.17** which means that between buyers and visitors, it shows that the two have a weak correlation.

## Recommendations
Based on the supermarket visitor categories that have been determined, we suggest the business team to **attract the attention of the Wandering Customers** category by interacting to introduce existing production. This type of visitor will pay close attention to the offer and it is not impossible after an interaction occurs, they decide to buy the product. 

Then for the **Loyal Customers category**, we recommend the business team to **maintain product quality, improve the best service and provide attractive rewards**. Because we assume that Loyal Customers are already engaged with the services or products that have been provided so they are difficult to move to other supermarkets.

And the last for the **Need-Based Customers category**, we recommend the business team to **build interest with visitor that the product matches with they needed**. So that we are expected they will purchase transaction process.

## Result Deployement
**MLflow** Tracking is an API and user interface component that records data about machine learning experiments and lets you query it. MLflow Tracking supports Python, as well as various APIs like REST, Java API, and R API.

You can use this component to log several aspects of your runs. Here are the main components you can record for each of your runs:

- Source : can be the name of the file that launches the run. Alternatively, if you are using an MLflow project, it can be the name of the project and entry point of the run.
- Code version : when using an MLflow Project, this would be the Git commit hash.
- Parameters : can be any key-value input parameters you choose, as long as the values and the keys are both strings.
- Artifacts : are output files (in all formats). Artifacts let you record images, PNGs for example, models (such as pickled scikit-learn models), and data files such as Parquet files.
- Start and end time : lets you record the start and end time of your run.
- Metrics : let you record key-value metrics containing numeric values. It is possible to update each metric throughout the duration of a run. This lets you, for example, track how the loss function of the model is converging. Additionally, MLflow lets you visualize the full history of each metric.

This deployment we use MLflow to track the model and we get some result, the results of the metrix evaluation for **RMSE** the value it is 2.9032768988296604. For **MEA** it is 2.30407177363699 with a **MAPE** of 6%. And for **R2**, the value is -0.17929580290702618.

The results of the evaluation matrix values in this deployment are the same as the evaluation values in the previous stage
