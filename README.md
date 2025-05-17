# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```py
import pandas as pd
df = pd.read_csv("Data_set.csv")
df
```
![image](https://github.com/user-attachments/assets/7ed041cb-0cd5-4ba3-84de-781004fc1044)
```py
df.describe()
```
![image](https://github.com/user-attachments/assets/d42f94f9-8e80-4bcb-80a9-3c9e1fd6a870)

```py
df.info()
```
```py
df.head()
```
```py
df.tail()
```
```py
df.isnull()
```
```py
df.isnull().sum()

```
```py
df.notnull()
```
```py
df.dropna(axis=0)
```
```py
df.fillna(0)
```
```py
df.fillna(method='bfill')
```
```py
df.fillna(method='ffill')
```
```py
df['watchers'].fillna(value=df['watchers'].mean())
```
```py
df['watchers'].fillna(value=df['watchers'].mean(),inplace=True)
df
```
```py
df['num_episodes'].fillna(value=df['num_episodes'].mean())
```
```py
df['num_episodes'].fillna(value=df['num_episodes'].mean(),inplace=True)
df
```
```py
df['rating'].fillna(value=df['rating'].mean())
```
```py
df['rating'].fillna(value=df['rating'].mean(),inplace=True)
df
```
```py
df['current_overall_rank'].fillna(value=df['current_overall_rank'].mean())
```
```py
df['current_overall_rank'].fillna(value=df['current_overall_rank'].mean(),inplace=True)
df
```
```py
df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean())
```
```py
df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean(),inplace=True)
df
```
```py
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
```py
sns.boxplot(data=af)
```
```py
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
```
```py
lb=q1-1.5*iqr
ub=q3+1.5*iqr
lb
```
```py
ub
```
```py
af=af[((af>=lb)&(af<=ub))]
af
```
```py
af.dropna()
```

```py
sns.boxplot(data=af)
```
```py
from scipy import stats
import numpy as np
data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df
```
```py
val=[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,258]

out=[]
def d_o(val):
    ts=3
    m=np.mean(val)
    sd=np.std(val)
    for i in val:
        z=(i-m)/sd
        if np.abs(z)>ts:
            out.append(i)
    return out

op=d_o(val)
op
```











# Result
          <<include your Result here>>
