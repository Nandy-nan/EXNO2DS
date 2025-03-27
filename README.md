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
```
```
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/59d0be4c-7bb7-47bb-8e0c-3eda655132c8)
```
df.info()
```
![image](https://github.com/user-attachments/assets/191bfa5e-a716-42a7-906d-e203a9810c24)
```
df.shape
```
![image](https://github.com/user-attachments/assets/657e3822-503c-495a-af3c-ce4cf32dde42)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/17eddd08-a223-4224-8839-919ffc9972d8)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/74bb9e3c-e835-4e1b-ae3c-45f4ba8eb98a)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2) # Changed 'value_couts' to 'value_counts'
per
```
![image](https://github.com/user-attachments/assets/46469cad-22fb-4801-95a3-c48de52ae54f)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/a4f2ce1c-bc43-480d-bc7b-1032f292ce1c)
```
df
```
![image](https://github.com/user-attachments/assets/cabd2301-1b1c-416d-b868-a0e50aaa67ad)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/57f2f032-1f1b-46c8-bc9b-24fea3a13924)
```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/f8375837-10ea-43fd-8861-a7f771626f19)
```
sns.catplot(x="Gender", col="Survived", kind="count", data=df, height=5, aspect=.7)
```
![image](https://github.com/user-attachments/assets/552ca546-93f5-4f68-8489-c23080ab9561)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/a98acbcb-8083-466e-9c9d-5990ff6d8692)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/2ae2d249-87fb-4c16-9ee3-c2f2ab995e34)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/ab02e303-2f4e-43de-9bff-6c4ef282f50a)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/c4c60212-b936-49cc-97a2-1f96ea2f7200)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/0274a9ef-455b-4e8c-b548-18eeab06bad0)
```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/66b249eb-1d85-4130-b1c2-08ce1e432c69)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/4b29a486-1f66-471d-a96f-effda81172e0)
```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/74d985f4-f141-4fe1-9cb9-5844778e17f8)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/de2fbadd-3c9c-4e29-af4a-053c34e65594)



# RESULT
      We have perfomed Exploratory Data Analysis on the given data set sucessfully.
