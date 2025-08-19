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

```
import pandas as pd
import numpy as np
df=pd.read_csv("C:\\Users\\admin\\Downloads\\Data_set (1).csv")
df.isnull()
```
<img width="1526" height="602" alt="image" src="https://github.com/user-attachments/assets/160ba616-9ffd-437d-ad57-f80abc717d04" />

```
df.notnull()
```
<img width="1520" height="613" alt="image" src="https://github.com/user-attachments/assets/a5fad12b-d0f9-4a2c-bcbe-ae55c3dec84b" />

```
df.tail()
```
<img width="181" height="287" alt="image" src="https://github.com/user-attachments/assets/bc2f05ba-6893-487c-a8e4-5c6363f6f4b0" />

```
df.info()
```
<img width="902" height="508" alt="image" src="https://github.com/user-attachments/assets/c6dc3812-1d4b-4bb0-9172-462511c8116f" />

```
df.describe()
```
<img width="1080" height="434" alt="image" src="https://github.com/user-attachments/assets/3ec8dffd-bd5f-429f-aba0-c16c69138de7" />

```
df.head(10)
```
<img width="1540" height="684" alt="image" src="https://github.com/user-attachments/assets/55fd26b0-38b9-430d-ba37-31fe1abc0d6e" />

```
df.dropna(axis=0)
```
<img width="1260" height="628" alt="image" src="https://github.com/user-attachments/assets/2ee55853-5771-4e0b-8aa7-c28f5edf1c18" />

```
df.dropna(axis=1)
```
<img width="583" height="431" alt="image" src="https://github.com/user-attachments/assets/9ff2ba62-f6bb-4b69-8de6-8040ad1a7d31" />

```
dfs=df[df['num_episodes']>20]
dfs
```
<img width="1065" height="687" alt="image" src="https://github.com/user-attachments/assets/c338fbec-1398-4ed8-80c0-e0a610a51339" />

```
dfs=df[df['show_name'].str.startswith(('A','F'))&(df['num_episodes']>25)]
dfs
```
<img width="1059" height="96" alt="image" src="https://github.com/user-attachments/assets/d427d751-053b-4295-9202-42e8a947b082" />

```
df.iloc[:3]
```
<img width="1044" height="134" alt="image" src="https://github.com/user-attachments/assets/dbfb168c-b630-4975-84fc-ff41e5616210" />

```
df.iloc[:4]
```
<img width="1033" height="152" alt="image" src="https://github.com/user-attachments/assets/643641dd-c00d-429e-aa6b-89161c2c180b" />

```
df['num_episodes']>20
```
<img width="440" height="228" alt="image" src="https://github.com/user-attachments/assets/75d2cc4c-d8a9-44c8-9153-6d29c71e677f" />

```
df.iloc[:3,3:]
```
<img width="724" height="124" alt="image" src="https://github.com/user-attachments/assets/a4c9b84d-1600-4d81-b5ad-6bfdd1bbd257" />

```
df.iloc[[1,2,3],[1,3,5]]
```
<img width="424" height="125" alt="image" src="https://github.com/user-attachments/assets/298fead8-85ad-4546-8cae-5e24ae603ddb" />

```
df.fillna("None")
```
<img width="1058" height="395" alt="image" src="https://github.com/user-attachments/assets/2d5c8622-ac25-4679-87e8-686b89050f25" />

```
ff=df.fillna(method='ffill')
ff
```
<img width="1070" height="387" alt="image" src="https://github.com/user-attachments/assets/4d701b1b-39a8-4318-a352-6ea3d253d7df" />

```
bf=df.fillna(method='bfill')
bf
```
<img width="1047" height="384" alt="image" src="https://github.com/user-attachments/assets/1283da49-f8e1-4381-a0cd-a19df18600a6" />

```
df.shape
```
<img width="439" height="64" alt="image" src="https://github.com/user-attachments/assets/9e0d868d-3546-49a6-8de1-5aea80a69898" />

```
fmean=df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean())
fmean
```
<img width="664" height="237" alt="image" src="https://github.com/user-attachments/assets/a4591374-97c7-494c-bed6-a289b1b61723" />

```
df.fillna(df['rating'].mean())
```
<img width="1075" height="526" alt="image" src="https://github.com/user-attachments/assets/05581b1e-2434-454a-9a58-5f9886159f44" />

```
df=pd.read_csv("C:\\Users\\admin\\Downloads\\SAMPLEIDS.csv")
df
```
<img width="955" height="623" alt="image" src="https://github.com/user-attachments/assets/a10c2a4f-cdce-432a-ae97-c066ad4784fe" />

```
df['GENDER'].value_counts()
```
<img width="277" height="69" alt="image" src="https://github.com/user-attachments/assets/606c6c70-e264-4a84-a457-66b86a227b2a" />

```
df.dropna(how='any').shape
```
<img width="252" height="56" alt="image" src="https://github.com/user-attachments/assets/fcf25b61-0269-4248-8244-e247401a1519" />

```
x1=df.dropna(how='any')
x1
```
<img width="995" height="526" alt="image" src="https://github.com/user-attachments/assets/3ae18c3c-f4a6-4334-98c8-64d9c8ebefd7" />

```
res=df.dropna(subset=['M1','M2','M3','M4'],how='any')
res
```
<img width="1058" height="504" alt="image" src="https://github.com/user-attachments/assets/8c2aa617-7529-4ce8-a6d8-df042a7f6915" />

```
mean=df.TOTAL.mean()
mean
```
<img width="147" height="60" alt="image" src="https://github.com/user-attachments/assets/6d23e211-d0ef-4ca4-8c5a-6ef2e45aba15" />

```
mn=df.TOTAL.fillna(mean,inplace=False)
mn
```

<img width="476" height="584" alt="image" src="https://github.com/user-attachments/assets/45b09254-e92c-4b9d-9882-b9bcab93f725" />

```
import pandas as pd
df = pd.read_csv("C:\\Users\\admin\\Downloads\\Loan_data.csv")
print(df.info())
```
<img width="744" height="609" alt="image" src="https://github.com/user-attachments/assets/4df7d1be-9234-42f5-a988-3ae1a63c3d08" />

```
print(df.describe())
```
<img width="1079" height="605" alt="image" src="https://github.com/user-attachments/assets/79c7c549-face-407a-af80-6b949dacdd62" />

```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from scipy import stats
age = [1, 3, 28, 27, 25, 92, 30, 39, 40, 50, 26, 24, 29, 94]
af = pd.DataFrame(age, columns=['Age'])
sns.boxplot(data=af, x='Age')
plt.show()
```
<img width="921" height="742" alt="image" src="https://github.com/user-attachments/assets/4bb2b986-bf72-4231-b52b-c2f9d28483d6" />

```
Q1 = af['Age'].quantile(0.25)
Q3 = af['Age'].quantile(0.75)
IQR = Q3 - Q1
lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR
outliers = af[(af['Age'] < lower_bound) | (af['Age'] > upper_bound)]
print("Outliers detected using IQR:")
print(outliers)
```
<img width="447" height="178" alt="image" src="https://github.com/user-attachments/assets/aea79bfc-51bf-4a57-b0dd-506d4fda4576" />

```
af_cleaned = af[(af['Age'] >= lower_bound) & (af['Age'] <= upper_bound)]
sns.boxplot(data=af_cleaned, x='Age')
plt.show()
```
<img width="927" height="768" alt="image" src="https://github.com/user-attachments/assets/4dc0f231-c1b3-4c83-bb97-3145e5aa922f" />

```
data = [1, 12, 15, 18, 21, 24, 27, 30, 33, 36, 39, 42, 45, 48, 51, 54, 57, 60, 63, 66, 69, 72, 75, 78, 81, 84, 87, 90, 93, 96, 99, 158]
df = pd.DataFrame(data, columns=['Values'])
sns.boxplot(data=df, x='Values')
plt.show()
```
<img width="914" height="785" alt="image" src="https://github.com/user-attachments/assets/da0008b3-4014-41ce-be39-49db7e8d9945" />

```
z_scores = stats.zscore(df)
outliers_z = df[(z_scores > 3) | (z_scores < -3)].dropna()
print(outliers_z)
```
<img width="210" height="100" alt="image" src="https://github.com/user-attachments/assets/d5fa4492-3288-418f-97e3-f12ffaaa0b8a" />

```
df_cleaned = df[(z_scores < 3) & (z_scores > -3)].dropna()
sns.boxplot(data=df_cleaned, x='Values')
plt.show()
```
<img width="913" height="778" alt="image" src="https://github.com/user-attachments/assets/63013304-a9f5-48f8-a807-e499d66a9b40" />

# Result

Thus the program to read the given data and perform data cleaning and save the cleaned data to a file was written and executed successfully.
