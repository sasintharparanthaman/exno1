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

# Coding and Output:
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![Screenshot 2024-03-01 101118](https://github.com/sasintharparanthaman/exno1/assets/145743219/b40850bb-4a61-4032-b527-339a634c6641)
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df.head()
```
![Screenshot 2024-03-01 101418](https://github.com/sasintharparanthaman/exno1/assets/145743219/3909a226-0f3b-4811-aeaa-3b62bd154a84)
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df.tail()
```
![Screenshot 2024-03-01 101525](https://github.com/sasintharparanthaman/exno1/assets/145743219/667b0779-6d1b-488e-a993-811ebe20e45f)
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df.isnull()
```
![Screenshot 2024-03-01 101742](https://github.com/sasintharparanthaman/exno1/assets/145743219/84492a40-ebb3-446f-93d1-bc792fb79a21)
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df.fillna(5)
```
![Screenshot 2024-03-01 101858](https://github.com/sasintharparanthaman/exno1/assets/145743219/ab0a177d-a1bd-40c6-8072-43f6b41b0a0e)

# Outlier Detection and Removal:
```
import seaborn as sns
import numpy as np
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![Screenshot 2024-03-05 051613](https://github.com/sasintharparanthaman/exno1/assets/145743219/98bbb5ec-cc8a-434f-b844-9746f0afc3ec)

```
sns.boxplot(data=af)
```
![Screenshot 2024-03-05 054226](https://github.com/sasintharparanthaman/exno1/assets/145743219/7c7a6352-6e7d-4269-baaa-69d627e11282)

```
sns.scatterplot(data=af)
```
![Screenshot 2024-03-05 054404](https://github.com/sasintharparanthaman/exno1/assets/145743219/6115d008-dbb0-4956-b6a7-c4f0e9c48cf3)

```
Q1=np.percentile(af,25)
Q3=np.percentile(af,75)
IQR=Q3-Q1
IQR
```
![Screenshot 2024-03-05 052237](https://github.com/sasintharparanthaman/exno1/assets/145743219/60ed0460-696b-4d6a-a1c3-6c142b114ab7)

```
lower_bound=Q1-1.5*IQR
upper_bound=Q3+1.5*IQR
outliers=[x for x in age if x< lower_bound or x>upper_bound]
print("Q1:",Q1)
print("Q3:",Q3)
print("IQR:",IQR)
print("Lower Bound:",lower_bound)
print("Upper Bound:"),upper_bound
print("outliers:",outliers)
```
![Screenshot 2024-03-05 052352](https://github.com/sasintharparanthaman/exno1/assets/145743219/3ee2b414-81b3-4427-9e75-769aced214da)
```
af=af[((af>=lower_bound)&(af<=upper_bound))]
af
```
![Screenshot 2024-03-05 054813](https://github.com/sasintharparanthaman/exno1/assets/145743219/a28a6ed3-4147-4f70-bcf3-139e4af355e6)

```
af.dropna()
```
![Screenshot 2024-03-05 054935](https://github.com/sasintharparanthaman/exno1/assets/145743219/9d8d0c37-6e84-4bbe-b986-275528b2789a)

```
sns.boxplot(data=af)
```
![Screenshot 2024-03-05 055029](https://github.com/sasintharparanthaman/exno1/assets/145743219/7428bca3-7210-4d6d-870c-04188760c1fc)

```
sns.scatterplot(data=af)
```
![Screenshot 2024-03-05 055140](https://github.com/sasintharparanthaman/exno1/assets/145743219/2da0ed2e-58c8-4199-9fc1-ffd4aef0e1c1)

```
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
data={'Weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df
```
![Screenshot 2024-03-05 055335](https://github.com/sasintharparanthaman/exno1/assets/145743219/8757b63c-5f42-41b1-a6e6-8a887b12c3f5)

```
z=np.abs(stats.zscore(df))
z
```
![Screenshot 2024-03-05 060059](https://github.com/sasintharparanthaman/exno1/assets/145743219/70e278d0-b45f-46c4-bdbf-7d0270b0c2db)

```
print(df[z['Weight']>3])
```
![Screenshot 2024-03-05 060227](https://github.com/sasintharparanthaman/exno1/assets/145743219/c917d559-4782-4950-8e3c-e157adc42b00)


# Result
Hence the Data Cleaning process is performed successfully on the given data using python code.
