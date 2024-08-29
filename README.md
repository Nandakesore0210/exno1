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

# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
