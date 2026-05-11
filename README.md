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
import seaborn as sns
data=pd.read_csv("/content/titanic_dataset.csv")
data
```

```
data.info()
```
<img width="420" height="288" alt="image" src="https://github.com/user-attachments/assets/cac9882a-9086-4832-8cc2-b422053c055f" />
<br>

```
data.describe()
```
<img width="420" height="288" alt="image" src="https://github.com/user-attachments/assets/1d03e2d6-ba22-4510-8ea5-08eefb1ef909" />
<br>

```
data.dtypes
```
<img width="438" height="382" alt="image" src="https://github.com/user-attachments/assets/b6ea820a-f7b2-40f3-a3b0-2cb945fb8f8b" />
<br>

```
data.shape
```
<img width="180" height="65" alt="image" src="https://github.com/user-attachments/assets/b037d542-406e-473a-91dc-e8defb31edc6" />
<br>

```
data.value_counts()
```
<img width="772" height="487" alt="image" src="https://github.com/user-attachments/assets/5f391c42-6c60-4c5b-be30-3967588b372e" />
<br>

```
data['Name'].value_counts()
```
<img width="551" height="402" alt="image" src="https://github.com/user-attachments/assets/bcf5a8ab-e159-4522-902d-84d7554a5d29" />
<br>

```
data.set_index("PassengerId") #or data.set_index("PassengerId", inplace=True)
data
```
<img width="778" height="476" alt="image" src="https://github.com/user-attachments/assets/f6120c0a-078e-4956-8e25-03add55f6604" />
<br>

```
data.nunique()
```
<img width="548" height="372" alt="image" src="https://github.com/user-attachments/assets/cab68338-607a-4b6d-9170-1031a4e87be6" />
<br>

```
sns.countplot(data=data,x='Survived')
```
<img width="683" height="386" alt="image" src="https://github.com/user-attachments/assets/ac78c2c8-72c6-4e37-ab57-e0947dd35c02" />
<br>

```
data.rename(columns={'Sex':'Gender','PassengerId':'P_ID'},inplace=True)
data
```
<img width="747" height="412" alt="image" src="https://github.com/user-attachments/assets/745e0a1e-4221-496a-8ac2-6269be631194" />
<br>

```
sns.catplot(x="Gender",col="Survived",kind="count",data=data)
```
<img width="770" height="408" alt="image" src="https://github.com/user-attachments/assets/121558e2-e29a-4fe8-b548-c40206c883c7" />
<br>

```
data.boxplot(column="Age",by="Survived")
```
<img width="601" height="391" alt="image" src="https://github.com/user-attachments/assets/36270c2f-3523-469a-b15c-ac31bec31815" />
<br>

```
sns.scatterplot(x=data["Age"],y=data["Fare"])
```
<img width="531" height="380" alt="image" src="https://github.com/user-attachments/assets/e7315e54-33ac-4402-8169-1ab53f5c3f58" />
<br>

```
plt=sns.boxplot(x='Pclass', y='Age', hue='Gender', data=data)
```
<img width="619" height="372" alt="image" src="https://github.com/user-attachments/assets/73675a57-e22f-4b8d-be26-b2070c98e5a5" />
<br>

```
sns.catplot(data=data, col="Survived", x="Gender", hue='Pclass', kind="count")
```
<img width="770" height="400" alt="image" src="https://github.com/user-attachments/assets/0a1c69e3-2fe5-41dd-a239-106b63c611c6" />
<br>

```
corr=data.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="555" height="384" alt="image" src="https://github.com/user-attachments/assets/0e49da2a-0a00-4fa2-a4a8-01374abe4001" />

# RESULT
Exploratory Data Analysis (EDA) was successfully performed on the given dataset using Python libraries. The data was analyzed using summary statistics and visualizations to identify patterns, relationships, missing values, and outliers in the dataset.
