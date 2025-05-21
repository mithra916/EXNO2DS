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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/83b8b545-e735-43a9-b0ac-e5477c0c34bc)

```
df.info()
```
![image](https://github.com/user-attachments/assets/2b7102e1-33e4-4cc9-b099-445477206c6e)

```
df.shape
```
![image](https://github.com/user-attachments/assets/a95a9c74-5322-4ce5-9fcc-ef6815a81944)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/262407ea-7fce-4e50-8f66-7e8745ccbb82)

```
df.shape
```
![image](https://github.com/user-attachments/assets/81e94cf1-b14e-4bea-9d32-63a67ef69634)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/43234795-156a-41b3-a0be-b3a831a0a87e)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/bfb83d59-2437-43b0-9aef-4bbf99cdf9d2)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/389a8df0-068b-4185-9b22-eb5a42c5d81a)

```
sns.countplot(data=df,x='Survived')
```
![image](https://github.com/user-attachments/assets/f71a1321-26e7-498f-9085-5038181b5678)

```
df
```
![image](https://github.com/user-attachments/assets/f5c46cef-92ad-462b-a32d-c83fb235ec90)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/d4081cb4-97b4-4404-9c05-aa840f52f39f)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/71c29d83-5985-44a5-8973-8f972b6a593e)

# Bivariate Analysis
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/dec3564b-e24d-44fc-9e99-e24d8adc2a8b)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/1605978a-14ec-4902-aea5-0cda4b6888a5)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/6d64617f-6ef3-4d3f-a6e4-c0a935a939cb)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/14bec40c-ed78-4737-9c67-b36879d06b9f)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/48634e32-db4e-44a1-a3d6-ca6396ae998a)

```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/d975a08c-f1a1-4567-a1dd-17446bbc7b5c)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/2f7423ce-2858-4fd7-a12f-142e968e97c3)

# Co-relation
```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/a74fab72-2ddc-4018-a278-a22fc83f2cf0)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/7d24efc3-50e1-4b3c-8334-71959e0f73be)

![image](https://github.com/user-attachments/assets/dccf2228-2535-4e52-8be6-c67b45f3a42d)

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
