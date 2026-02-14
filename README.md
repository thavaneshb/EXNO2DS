# EXNO2DS
# reg no : 212224040352
# name   : THAVANESH B 
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
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```python
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/d0bf3ff2-4e7c-45d9-ac78-760c290dc7b4)
```python
dt.info()
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/4bbc1405-d6f5-4509-9b20-2d37ce4478ba)
```python
dt.shape
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/9b09ae8d-e0ac-46fe-bb3d-a0b71287f577)
```python
dt.set_index("PassengerId",inplace=True
dt.describe(
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/61054be6-de83-445a-95fb-f7730db821fd)
```python
dt.nunique()
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/88bb2592-2544-4b9d-a716-b5eb8fffafcc)
```python
dt["Survived"].value_counts()
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/d81298a9-4561-43ee-9df5-dc4bb11d1336)
```python
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/d2c70fe5-98be-4227-8344-c590708e5a2e)
```python
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/c3a44777-5cbb-417e-a2ce-5266e58fc788)
```python
dt
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/093352ea-339d-483b-b547-432f84cc7651)
```python
dt.Pclass.unique()
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/7d0c655b-d9eb-4dd6-8483-45cdd309236e)
```python
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/5eeb22a5-6f5d-4aa8-b868-799c95824f5c)
```python
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5, aspect=.7)
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/e7a3ce46-314a-4346-b03d-1f01b25431c2)
```python
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/b8b9e2df-f728-4bbb-9c81-0d9f7d6f8978)
```python
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/42fa5728-4cd6-470c-a162-d1c511d91c8d)
```python
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/2cf9d440-ee05-45e4-a6d8-ae53b96d8b8d)
```python
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/0a6a0143-18d5-4704-9c09-ae0e18a1bd78)
```python
import matplotlib.pyplot as plt
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/589439a9-0d83-4691-9b0e-9e01328ccf17)
```python
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/f7be6c83-3155-462d-9159-fd9afb5c3646)
```python
#co-relation
import seaborn as sns
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/95281acc-eb98-4a1c-a34e-eb24f1f43d92)
```python
sns.pairplot(dt)
```
![image](https://github.com/Augustine0306/EXNO2DS/assets/119404460/1942a8ca-2775-48c2-bf72-599ec5a4e6c6)

# RESULT
Therefore, the code is successfully executed.
