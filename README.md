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
![image](https://github.com/user-attachments/assets/55e9e69d-10bf-405f-932f-437f6a634db0)
```
df.info()
```
![image](https://github.com/user-attachments/assets/f4ade02b-e41d-45d8-9e82-2bb21ea4b692)
```
df.shape
```
![image](https://github.com/user-attachments/assets/1fd80662-7475-4908-8edf-492ac3bc466a)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/a8ea4954-c52a-44fe-8feb-3611a37120ab)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/701f297a-ce64-4f0f-9731-bb49af27eba4)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2) # Changed 'value_couts' to 'value_counts'
per
```
![image](https://github.com/user-attachments/assets/7468c294-29c8-4301-8d49-50c1e8a153fb)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/85e4005f-9b14-4726-be6d-44077b0042f6)
```
df
```
![image](https://github.com/user-attachments/assets/3190e0d5-4f63-4ad8-ac96-f2f91fefaa90)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/ed4ae65e-22cc-4fd7-a21a-07097e096ccb)
```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/41f38892-06e6-4137-8c69-47d6dd0b0557)
```
sns.catplot(x="Gender", col="Survived", kind="count", data=df, height=5, aspect=.7)
```

![image](https://github.com/user-attachments/assets/1494aeab-e3ed-409c-bd0f-d185ca47e988)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/053824e8-68c9-48f9-949a-0c5b61ba24a5)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```

![image](https://github.com/user-attachments/assets/8df43ecd-0ed3-40a9-bf19-1ba63a1f2c83)
```
df.boxplot(column="Age",by="Survived")
```

![image](https://github.com/user-attachments/assets/4e871adb-c5f5-4f16-8135-0ef3a49b1167)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

![image](https://github.com/user-attachments/assets/bebee9a3-f7fd-4cff-9291-b072e972a4d5)
```
sns.jointplot(x="Age",y="Fare",data=df)
```

![image](https://github.com/user-attachments/assets/dd3e1939-58a5-42c3-8e07-c35e11ceaaaf)
```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

![image](https://github.com/user-attachments/assets/7532afd6-b019-4804-894d-355489188a9a)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/user-attachments/assets/a06b3a29-d055-4b68-b7fb-4fcc9e8fc3ec)
```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/9f89618b-ff6d-4d1e-81bc-f8c1f7b422f6)
```
sns.pairplot(df)
```

![image](https://github.com/user-attachments/assets/32560a99-dd58-4be4-bc56-cec6a96c63cd)

# RESULT
        we have performed Exploratory Data Analysis on the givewn set data analysis.
