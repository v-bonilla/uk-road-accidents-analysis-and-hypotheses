# A brief analysis of the UK road accidents data and testing of hypotheses
### Team Dataholics - Coursework for Practical Business Analytics
### MSc. in Data Science 2019/20 - University of Surrey

Contributors to this project are:
- Hannes Kastenhuber
- Benjamin Baxter
- Victor Bonilla
- Luxman Elangeswaralingam
- Konstantinos Kompogiannopoulos
- Aiden Aslam
- Prof. Nick Ryman-Tubb

### Table of content

1. [Introduction and aims of the project](#introduction-and-aims-of-the-project)
2. [Data source of the project](#data-source-of-the-project)
3. [Files in this project](#files-in-this-project)

## Introduction and aims of the project

The aim of this report is to analyse car accidents that have occurred in the UK in the period 2005-2015 to give insight into the question: ”How can the UK government use its collected data to improve road safety?”

The UK government provides detailed road safety data with respect to personal injury, road accidents, the types of vehicles involved and casualties (if any). The collected data only includes incidences that are reported to the police and recorded using the STATS19 accident reporting form. The data used in this analysis was obtained from the [UK
government website](#data-source-of-the-project).

This report considers ‘Cross-Industry Standard Process for Data Mining’ (CRISP-DM), widely used for data mining and business analytics projects. It is worth noting, before a more detailed description of the data, the obvious problem presented is the total number of accidents happening in the UK every day. More specifically, the number of high severity accidents with casualties. It is known than accidents do not happen randomly without a cause. Human errors are the most common reasons as to why accidents occur. As a result, this report’s hypotheses are based on the assumptions that a combination of a variety of internal and externals factors presented in the data can cause a car journey to result in an accident:

1. Environmental factors including the location and quality of the road and weather information directly influence the likelihood of an accident to happen:
    - This can help the UK government to better allocate resources for road improvement in order to decrease the number of accidents.
2. Seasonality of the number of accidents:
    - This can help the government to identify parts of the year when additional support and control is needed on UK streets to prevent accidents.
3. Age of the driver and accident characteristic:
    - This can help identify what accident features are common amongst different age groups and thus help ways to improve the education of drivers and thus prevent accidents.

## Data source of the project

The data of the project is gathered from an unique source:

- UK Department for Transport. [Road safety data](https://data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data), 2016.

## Files in this project

### uk_road_accidents_analysis_and_hypotheses_report.pdf

The complete report of this project.

### Functions_Dataholics.R 

Contains mainly own written functions. Also contains some of the functions written by Prof. Nick F Ryman-Tubb, presented to us in the computer labs. 

### main.R 

Executes the program. Has each needed filename as a global variable. Reads in the functions file, installs the needed packages and executes the different parts of the program.

You will be asked to enter your JAVA_HOME path. On Windows there was a slight issue regarding the file path. Changing the path to “C:/Program Files/Java/jre1.8.0_161” fixes the issue should it occur.

### Cleaning.R 

This file reads in the original data files, drops not needed columns and drops entries with NULL values or certain, pre discussed values. 

Delivers a bar graph for each parameter and compares the distribution of original and cleaned data set’s Accident_Severity. 

All steps are described inside the report. 

### Combining_Aggregating.R 

Changes Junction_Control value based on the value of Junction_Detail. 

Combines some values of certain columns. 

Will also deliver a comparison of the Accident_Severity between the original and the cleaned data sets. 

All steps are described inside the report. 

### Prediction_Parameter.R 

You will be asked if you want to execute your own clustering or if you just want to execute the hard-coded clustering we prepared. 

By typing “y” and pressing enter, you will execute your own kmeans cluster calculation for 2 to 15 clusters, 3 times, to plot the variances for the different cluster numbers. 

After that a kmeans cluster will be performed on the local minimum of 8 clusters with 2500 starting points. This will produce a similar cluster to the one we decided for and hard-coded. 

That will be executed afterwards. 

### TimeAnalysis_Hyp2.R 

Executes the analysis on the time data (Hypothesis 2 of the report) 

### AgeAnalysis_Hyp3.R 

To run k-means clustering for different values of k which increases run time significantly (total runtime ~10 mins) first ensure the global variable “Multi_k_Plot” is set to TRUE. Then type “y” when prompted. To disable this set “Multi_k_plot” to FALSE please press ENTER when prompted. 

### EnvironmentAnalysis_Hyp1_Regression.R 

Executes a multivariate linear regression, a mars regression and a mars regression with cross validation of both the Accident_Severity and the Custom_Severity, created in Prediction_Parameter.R 
