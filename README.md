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
## df=pd.read_csv("SAMPLEIDs.csv")
![Screenshot 2024-08-29 160423](https://github.com/user-attachments/assets/976326b8-001c-4441-bf13-16596556c6c9)

## df=pd.read_csv("SAMPLEIDs.csv")
## print(df.head(5))
![image](https://github.com/user-attachments/assets/b69bb25c-5896-4fcd-abe3-e2b1afddd0de)

## df.tail(2)
![image](https://github.com/user-attachments/assets/421abd49-9a4c-4ec3-ac6e-9163d1fa4c48)

## df.info()
![image](https://github.com/user-attachments/assets/741bef3a-4ea8-46f1-8e60-afcb04ad604a)

## df.describe()
![image](https://github.com/user-attachments/assets/87821c98-e4ba-4096-ad1a-68f555864d61)

## df.shape
![image](https://github.com/user-attachments/assets/a276f62d-78a5-4000-be8d-cd2438651c20)

## df.isnull().sum()
![image](https://github.com/user-attachments/assets/de4bfe8c-5e1f-408c-be1f-2887bc899fc0)

## df.dropna(how='any').shape
![image](https://github.com/user-attachments/assets/fe4fef51-01df-4a23-a4dc-5636ba603a5e)

## x=df.dropna(how='any')
![image](https://github.com/user-attachments/assets/8b203015-8b49-4229-b138-fdc73a638d97)

## df.nunique()
![image](https://github.com/user-attachments/assets/7dd756a6-3cc3-4083-8ef7-414405377ea9)

## x2=df.dropna(how='all').shape
![image](https://github.com/user-attachments/assets/8548af30-19c1-441e-a737-ecafc4a1d427)

## tot=df.dropna(subset=['TOTAL'],how='any')
![image](https://github.com/user-attachments/assets/44720231-4eb0-456b-b0b6-d3fc6dc9f0e5)

## tot=df.dropna(subset=['M1','M2','M3','M4'],how='any')
![image](https://github.com/user-attachments/assets/f8a44c64-4314-425c-9fbb-d2f1291c4276)

## s=df.fillna(0)
![image](https://github.com/user-attachments/assets/0e67c9e3-e0e4-427a-9869-8d6dde192ce9)

## df.isna().sum()
![image](https://github.com/user-attachments/assets/604c28d3-f4ab-4f63-952b-2d295bb1dfc9)

## df['M2']
![image](https://github.com/user-attachments/assets/bba6ea3d-cd94-4c83-89e0-ba1c9f997db5)

## df.isnull()
![image](https://github.com/user-attachments/assets/19537a1f-5660-4c15-ab48-237f378c9d0a)

## df.notnull()
![image](https://github.com/user-attachments/assets/1e45fa1e-dc1a-42a9-a5f5-65e42c6f8f0b)

## xl=df.dropna(axis=0)
![image](https://github.com/user-attachments/assets/1ca909a3-e7b0-4d88-b5b3-0902396e75ed)

## df.duplicated()
![image](https://github.com/user-attachments/assets/7ae9b5fc-d1bc-48c1-8a3e-fd1ec2cb34de)

## m=df.drop_duplicates(inplace=False)
![image](https://github.com/user-attachments/assets/bf88236f-9288-4d40-86fc-30e15eefe1ab)

## sns.heatmap(df.isnull(),yticklabels=False,annot=True)
![image](https://github.com/user-attachments/assets/afcb778c-a0e1-41a8-92c6-31baea754a9e)

## sns.heatmap(df.notnull(),yticklabels=False,annot=True)
![image](https://github.com/user-attachments/assets/a0b55d00-8d68-44ea-bebb-61879c19f7a6)

## df.dtypes
![image](https://github.com/user-attachments/assets/660e76c9-eef1-4468-b894-2528e6aa10d4)

```
import pandas as pd
import seaborn as sns
import numpy as np
age=[1,24,13,14,18,39,76,67,54,3,21,34,26]
af=pd.DataFrame(age)
af
```
![image](https://github.com/user-attachments/assets/3f77b115-24df-42a5-a447-7474629bb6e8)

## sns.boxplot(data=af)

![image](https://github.com/user-attachments/assets/39dee2fe-0639-4266-a715-26c4e15e7de7)

## sns.boxenplot(data=af)

![image](https://github.com/user-attachments/assets/783f7d16-a1ea-4ba2-9733-c552c20108c8)

## sns.scatterplot(data=af)

![image](https://github.com/user-attachments/assets/0dcb599c-6863-402b-b1de-bb64a2401ac0)

```
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iq=q3-q1
print(iq)
```
![image](https://github.com/user-attachments/assets/550d394e-be36-455c-a66e-a8df7436cf02)

```
q1=np.percentile(af,25)
q2=np.percentile(af,75)
iq=q2-q1
print(iq)
```
![image](https://github.com/user-attachments/assets/59cd08f4-8d2d-48c5-bf4f-6dcff5bfea6f)

```
lower_bound=q1-1.5*q3
upper_bound=q2+1.5*q3
print(lower_bound)
print(upper_bound)
print("Q1",q1)
print("Q3",q3)
```
![image](https://github.com/user-attachments/assets/5b574fd1-d259-4994-8115-2ec1bbf95f92)

## af=af[((af>=lower_bound)&(af<=upper_bound))]

![image](https://github.com/user-attachments/assets/ed4711dd-403b-4ab3-9327-29f007078927)

## sns.boxplot(data=af)

![image](https://github.com/user-attachments/assets/6d5cbdee-64e5-4863-b0d6-3bc604ce46c5)

```
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
df=pd.read_csv('iris.csv')
df
```
![image](https://github.com/user-attachments/assets/2c83a5d9-d94a-438c-aebd-fc61443406e6)

## sns.boxplot(x='sepal_width',data=df)

![image](https://github.com/user-attachments/assets/35badff3-07c2-495e-a191-5a2ffb3ce65e)

```
c1=df.sepal_width.quantile(0.25)
c3=df.sepal_width.quantile(0.75)
iq=c3-c1
```
![image](https://github.com/user-attachments/assets/c11e62b1-66cf-4a16-bccc-ff9fab2b8e21)

```
rid=df[((df.sepal_width<(c1-1.5*iq)))|(df.sepal_width>(c3+1.5*iq))]
rid['sepal_width']
```
![image](https://github.com/user-attachments/assets/31c88a54-2e6f-4486-a5b7-090cb59f5190)

## delid=df[-((df.sepal_width<(c1-1.5*iq))|(df.sepal_width)>(c3+1.5*iq))]

![image](https://github.com/user-attachments/assets/6eb97bb8-dd27-41be-98f3-b141f4500259)

## sns.boxplot(x='sepal_width',data=delid)

![image](https://github.com/user-attachments/assets/3de6cac3-208f-4274-9f12-2f7e280baa54)

# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
