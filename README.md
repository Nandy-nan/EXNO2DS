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
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
![image](https://github.com/user-attachments/assets/abd29309-f9d1-48fa-9987-18724c6e6a49)
```
df.info()
```
![image](https://github.com/user-attachments/assets/84751422-12e1-4eda-90c3-9676468b6c55)
```
df.shape
```
![image](https://github.com/user-attachments/assets/e0505a25-20ee-42c6-bb17-fa9c379fbccc)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/0b20b91f-3140-4a68-a2d7-eb0b0b69a4eb)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/6e732980-fafe-4305-83bd-a98e7ed58481)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2) # Changed 'value_couts' to 'value_counts'
per
```
![image](https://github.com/user-attachments/assets/813f8398-cdb0-44ca-8ac4-154c8ae12b94)
```
sns.countplot(data=df,x="Survived")
```

![image](https://github.com/user-attachments/assets/2d65a054-6bd2-4fa8-91a8-3db775c7d319)
```
df
```
![image](https://github.com/user-attachments/assets/5954d6fe-9369-4b04-bc35-c7df7eae412c)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/9f77f903-16ce-4384-a7a7-59a17fe4d8a8)
```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```

![image](https://github.com/user-attachments/assets/8e446a20-526c-43a4-a6dd-d51b26728e78)
```
sns.catplot(x="Gender", col="Survived", kind="count", data=df, height=5, aspect=.7)
```

![image](https://github.com/user-attachments/assets/62279287-cdb6-4d43-afee-71f666297156)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/379a3e98-411f-4e26-a6ea-e8c601c6f736)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/78eb2e1b-022c-4a32-b19d-52dbb4c05f22)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/2ad147f9-7ddc-4b01-8fb0-ef14ad80d60d)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/0128b0bd-3957-4f73-bf0f-6cf8a7c8333b)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/24894214-ed1d-461a-9c35-3115598c0054)
```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/c49b80a4-9908-4765-b968-9f078eab33f1)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/8c347f11-576f-417a-9134-f505a9077ee9)
```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/d7418b33-6da3-4b7f-bec6-58a0aa5d8d41)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/d275f274-7a08-45ec-bc7c-ee7d76aec3ee)


# RESULT
we have performed Exploratory Data Analysis on the given data set sucessfully.
