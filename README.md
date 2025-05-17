# Exno:1
Data Cleaning Process

<h3> NAME : Abdur Rahman Basil A H</h3>
<h3> REG NO : 212223040002</h3>

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
![image](https://github.com/user-attachments/assets/77068cbd-ee4c-4f87-a927-d4cea39d50de)

```py
df.head()
```
![image](https://github.com/user-attachments/assets/da86fb33-9bc0-47be-a38c-239ac32acc82)

```py
df.tail()
```
![image](https://github.com/user-attachments/assets/4a8c934b-6d0d-4071-914f-4534c58bc397)

```py
df.isnull()
```
![image](https://github.com/user-attachments/assets/d046acf6-bc09-47a9-b6a5-856d73b7b6a2)

```py
df.isnull().sum()

```
![image](https://github.com/user-attachments/assets/d002ab75-6972-4ec5-acc4-129cd922b506)

```py
df.notnull()
```
![image](https://github.com/user-attachments/assets/c4ba2385-f7ba-4908-b782-32535f57982f)

```py
df.dropna(axis=0)
```
![image](https://github.com/user-attachments/assets/33f0d8cc-1d37-4a33-a222-145afe126a5c)

```py
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/4b278579-d4a0-43a6-a247-c3506b9c59eb)

```py
df.fillna(method='bfill')
```
![image](https://github.com/user-attachments/assets/37e8e187-c5f2-46cb-8978-2d783bd1892d)

```py
df.fillna(method='ffill')
```
![image](https://github.com/user-attachments/assets/1ef6c702-f5d4-4fbb-bf60-687be982442d)

```py
df['watchers'].fillna(value=df['watchers'].mean())
```
![image](https://github.com/user-attachments/assets/e5011235-319a-4a12-890a-1573bde1d02c)

```py
df['watchers'].fillna(value=df['watchers'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/7f743ba0-7896-41c9-8750-787e6411a1e3)

```py
df['num_episodes'].fillna(value=df['num_episodes'].mean())
```
![image](https://github.com/user-attachments/assets/507b694e-7906-4bbd-8701-4c25af87ea31)

```py
df['num_episodes'].fillna(value=df['num_episodes'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/08ab194e-00df-4a1f-85a1-d968fbdd090b)


```py
df['rating'].fillna(value=df['rating'].mean())
```
![image](https://github.com/user-attachments/assets/9daf5c04-1513-4e2f-bfc1-7bf83bca0e72)

```py
df['rating'].fillna(value=df['rating'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/ecd7c424-7173-4f6f-b231-a71686b98100)

```py
df['current_overall_rank'].fillna(value=df['current_overall_rank'].mean())
```
![image](https://github.com/user-attachments/assets/8278e5b8-1be2-4968-8344-0d2091a1283e)

```py
df['current_overall_rank'].fillna(value=df['current_overall_rank'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/dd067e31-7ed3-492f-986b-de8da6704752)

```py
df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean())
```


![image](https://github.com/user-attachments/assets/ff99d368-2086-4e0d-9fe7-c13f474627a8)

```py
df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean(),inplace=True)
df
```

![image](https://github.com/user-attachments/assets/1f24aec2-3c63-49ba-b966-655bb8809140)

```py
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```

![image](https://github.com/user-attachments/assets/760d3cd5-c2c5-49f5-9f74-e260c6320fbf)

```py
sns.boxplot(data=af)
```

![image](https://github.com/user-attachments/assets/e40a0403-0d4c-4ad3-a0fa-8e2310b11b86)

```py
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
```

![image](https://github.com/user-attachments/assets/88d5b492-928f-4205-9679-e8982d5f86fe)

```py
lb=q1-1.5*iqr
ub=q3+1.5*iqr
lb
```

![image](https://github.com/user-attachments/assets/4a072481-6823-4494-a2d8-27f8dd1e6e52)

```py
ub
```

![image](https://github.com/user-attachments/assets/8b8d5bc0-dfe1-4816-939a-e17ea9ca18dd)

```py
af=af[((af>=lb)&(af<=ub))]
af
```

![image](https://github.com/user-attachments/assets/dc030c9a-e0fd-47a3-beb4-c8008ba772e3)

```py
af.dropna()
```

![image](https://github.com/user-attachments/assets/19a344ab-84ed-453f-a228-13dd4231c7ee)


```py
sns.boxplot(data=af)
```

![image](https://github.com/user-attachments/assets/8c82af3d-80be-47e5-8b18-553ccedc2672)

```py
from scipy import stats
import numpy as np
data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df
```

![image](https://github.com/user-attachments/assets/9264fa2c-c0fb-4f44-906c-122ae43080ab)

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

![image](https://github.com/user-attachments/assets/c7f7f146-415a-42bc-bcbf-2d1eed8051eb)












# Result
Thus, the Data Cleaning Process is executed Successfully.

