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
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/23008859/exno1/assets/139117979/f23e247c-5c3b-415b-984d-86f297773ba7)

```
print(df.head(7))
```
![image](https://github.com/23008859/exno1/assets/139117979/a1c6f0ee-aea4-465b-8060-83aeca28f303)

```
print(df.tail(2))
```
![image](https://github.com/23008859/exno1/assets/139117979/97f31dde-6231-42cd-8181-96d752ef291e)

```
df.info()
```
![image](https://github.com/23008859/exno1/assets/139117979/61199b93-358e-4e93-ab38-5af9b47c207e)

```
print(df.describe())
```
![image](https://github.com/23008859/exno1/assets/139117979/890e73a9-2ad1-4d96-9b24-fdc4aa7c94e0)

```
df.isnull().sum()
```
![image](https://github.com/23008859/exno1/assets/139117979/86bec09e-8594-40ff-bee7-598c817458e7)

```
df.nunique()
```
![image](https://github.com/23008859/exno1/assets/139117979/2d1a57a3-5669-4cfc-a3a7-57e46fa9453e)

```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/23008859/exno1/assets/139117979/349c6e8c-4235-45cc-adca-2565995d5f72)

```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/23008859/exno1/assets/139117979/2e1da6e0-6393-4038-804a-590bb427034c)

```
min=df.M4.min()
min
```
![image](https://github.com/23008859/exno1/assets/139117979/d0e758f3-4d00-4a50-9dd2-a213b4b2df98)

```
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/23008859/exno1/assets/139117979/b57b8c89-a6b7-4a47-9d19-eb31288a7664)

```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/23008859/exno1/assets/139117979/274fdaf0-3da0-47f0-bd4f-6c4ecd92aefc)

```
sns.boxplot(data=af)
```
![image](https://github.com/23008859/exno1/assets/139117979/562e37f9-f6e1-4e13-b0ca-569eccb629ae)

```
sns.scatterplot(data=af)
```
![image](https://github.com/23008859/exno1/assets/139117979/a1ed10df-171f-4863-ab98-5b191ece32d5)

```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![image](https://github.com/23008859/exno1/assets/139117979/14763504-4507-4f1f-a3bf-3d5dd175ceb9)

```
af=af[((af>=low)&(af<=high))]
af
```
![image](https://github.com/23008859/exno1/assets/139117979/2a483ac2-a588-4d87-abf6-3d19cc3c9a80)

```
af.dropna()
```
![image](https://github.com/23008859/exno1/assets/139117979/017bf302-4cda-4df1-8df2-dfbdd2bc2c4d)

```
sns.boxplot(data=af)
```
![image](https://github.com/23008859/exno1/assets/139117979/ffdfd574-7b76-4900-bf9e-c7438a189551)

```
sns.scatterplot(data=af)
```
![image](https://github.com/23008859/exno1/assets/139117979/0b09fa28-f385-4a1b-bde8-b532e1c296a8)

```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![image](https://github.com/23008859/exno1/assets/139117979/cd93d629-b1a4-4b36-9214-a10a02a9377b)

```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![image](https://github.com/23008859/exno1/assets/139117979/9aa1f58f-cea0-48ff-aca2-8e2d6714dde1)

# Result
Thus the given program executed successfully.
