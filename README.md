# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
dt=pd.read_csv("/content/titanic_dataset (2).csv")
```
```
dt
```
![image](https://github.com/user-attachments/assets/a5cd1d97-7a24-4f2e-9227-e9bc5844236a)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/4279ab87-1b8c-4a88-8c20-e2b957fe5a37)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/92420563-13f9-4efb-a7a6-24012046f070)
```

dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![image](https://github.com/user-attachments/assets/24cff254-849e-4d5a-81df-7ac29d3b2615)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/a6dcbb7a-9a48-4eae-99be-5a95d24e381f)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/840066e4-37e3-4c2b-b1c8-84523d90f3f8)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/6e8cd551-52ba-4cb3-ba1f-dc3e6460dffa)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/447e2dcc-c47e-48a6-9ae3-96474447f145)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/8fc69635-184d-4bc1-b743-78fa8d794161)
```
dt
```
![image](https://github.com/user-attachments/assets/713314cc-d38c-4270-a04c-65e6e63bd7ca)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/c5662e8e-f6bd-4e0b-befd-5bf96c2712e0)
```
dt.rename(columns={'Sex':'Gender'},inplace = True)
dt
```
![image](https://github.com/user-attachments/assets/28276fc6-1584-4115-86c3-4a81aaf4baaf)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/fd646119-7385-4c4d-a0b8-e64746e87337)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/user-attachments/assets/c0771753-2d30-4db1-b55c-5857d226654d)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/0260e754-2dce-4d8a-acb8-86768056c022)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/5d331aa0-7a17-47a6-ade4-14c6c882a3cc)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/d586515b-f132-40d4-bed1-cfab1572c8a4)
```
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![image](https://github.com/user-attachments/assets/7703773c-adf2-485f-9718-2fe5492be6fd)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/1d4f3462-9ebf-4f9f-954a-02d410ea7630)
```
##co-relation
 numeric_dt=dt.select_dtypes(include=['int64', 'float64'])
 corr = numeric_dt.corr()
 sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/f51fc41a-6553-4970-8ca5-abc089c1f542)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/5ea732f2-0ec0-4f0d-964b-67f2eb463b6e)
![image](https://github.com/user-attachments/assets/14ec1e1a-5495-41e5-99d2-3cd4e4ceaaeb)
```
RESULT:
    Thus , we have performed the Exploratory data anlaysis on the given data.




