![header](https://capsule-render.vercel.app/api?type=waving&height=190&section=header&text=%20Machine%20Learning%20Operations%20(MLOps)%20Project&fontSize=30&&color=957DAD&fontColor=ffffff&fontAlignY=35)


## Index 
<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#Index">Index</a></li>
    <li><a href="#Introduction">Introduction</a></li>
    <li><a href="#Objective">Objective</a></li>
    <li><a href="#Scope">Scope</a></li>
    <li><a href="#Tech Stack">Tech Stack</a></li>
    <li><a href="#ETL">ETL</a></li>
    <li><a href="#EDA">EDA</a></li>
    <li><a href="#API Functions">API Functions</a></li>
    <li><a href="#Recommendation System">Recommendation System</a></li>
    <li><a href="#Deployment">Deployment</a></li>
    <li><a href="#Developer">Developer of the project</a></li>
    <li><a href="#Video">Video</a></li>
  </ol>
</details>


## Introduction 
<p align="justify">
This is my MLOps project for the Data Science career at the Soy Henry academy. </br>

This project leverages data from a comprehensive movies dataset, comprising information such as movie titles, genres, release dates, ratings, and more. It utilizes different techniques in ETL (Extract, Transform, Load), exploratory data analysis (EDA), and API development to deliver accurate movies recommendations.
</p>

## Objective
The primary objective this project is to develop and deploy a content-based movie recommendation system by leveraging data from a comprehensive movies dataset. 
The project aims to achieve the following specific objectives:
- Data Transformation and Cleansing: Apply Extract, Transform, Load (ETL) techniques to preprocess and cleanse the movies dataset.
- Exploratory Data Analysis (EDA): Conduct in-depth exploratory data analysis to gain insights into movie attributes such as title, overview and genres. Identify key features that significantly influence movie preferences and uncover patterns that can be leveraged for accurate recommendations (I chose myself as target audience so this part of the project might be kind of biased). 
- API Development: Design and implement a set of functions and an API that seamlessly integrate with the content-based recommendation system.
- Recommendation Generation: Develop a machine learning model that utilizes content-based filtering techniques and similarity scores to recommend movies with similar attributes to the one given by the user.
- API Deployment: Deploy the recommendation system's API in a production environment, ensuring it is available and accessible to users. Implement appropriate scaling mechanisms to provide a seamless user experience.
- MLOps Best Practices: Establish an efficient MLOps infrastructure.

## Scope
The project was developed following these key aspects:
- Data Preprocessing: [ETL link](https://github.com/ksfajardo/PI01_ML_OPS/blob/main/ETLPI01.ipynb)
- API Functions Development: [API Functions Development link](https://github.com/ksfajardo/PI01_ML_OPS/blob/main/FuncionesAPI.ipynb)
- Exploratory Data Analysis: [EDA link](https://github.com/ksfajardo/PI01_ML_OPS/blob/main/EDA_ML.ipynb)
- Machine Learning Model Development: [Machine Learning Development link](https://github.com/ksfajardo/PI01_ML_OPS/blob/main/MLmodel.ipynb)
- API Development: [API Repository](https://github.com/ksfajardo/PI01_ML_OPS_API) (This is located in a different repository here in my github but this is purely to keep an order for myself)
- API Deployment: [API Deploy](https://moviesapp-oxeinkhcia-uc.a.run.app) (You can add "/docs" at the end of the link to go to the automatic documentation FastAPI creates)

## Tech Stack
![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Google Cloud](https://img.shields.io/badge/GoogleCloud-%234285F4.svg?style=for-the-badge&logo=google-cloud&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)
![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)

## ETL
The ETL process was performed on the given dataset to prepare it for analysis and querying, following the steps below:
1. To streamline the dataset and focus on relevant information, unnecessary columns including "video," "imdb_id," "adult," "original_title," "vote_count," "poster_path," and "homepage" were removed. 
2. Null values in the "revenue" and "budget" fields were replaced with 0, ensuring consistency in calculations. Null values in the "release date" field were removed to ensure data integrity.
3. To standardize the format, dates were transformed into the YYYY-mm-dd format. Moreover, a new column called "release_year" was created to extract the year from the release date, providing a separate field for temporal analysis.
4. A crucial metric, return on investment, was computed by dividing the revenue by the budget for each entry, resulting in a new column called "return." When data was unavailable to calculate the return, it was assigned a value of 0, maintaining consistency in the dataset.
5. The dataset contained nested fields such as "belongs_to_collection" and "production_companies," which needed to be unnested for easier data manipulation. 

All of this was developed locally in VSCODE using Jupyter Notebook files, python, numpy and pandas.

## EDA
The resulting data from the ETL was used to conduct the Exploratory Data Analysis. All of the columns were analyzed with the help of the ydata_profiling library. Decisions like what to do with missing values, outliers and more were taken. Identifying patterns and relevant attributes was a vital step in setting the foundation for the subsequent development of the API Functions and the Recommendation System.

All of this was developed locally in VSCODE using Jupyter Notebook files, python, numpy, pandas, matplotlib, seaborn, wordcolud and ydata_profiling.

## API Functions
In this part of the project, the requested endopints were developed as python functions in a Jupyter Notebook file. Then, a main.py file was created with the structure needed to deploy them locally on the FastAPI and uvicorn services. These functions take as data source the csv file resulting from the EDA. I did not create a virtual enviroment to test this, since I already had all the required libraries installed in my machine, I felt it was unnecesary.

All of this was developed locally in VSCODE using Jupyter Notebook files, python, numpy, pandas, FastAPI and uvicorn.

## Recommendation System

## Deployment

## Developer

## Video
