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



# Result
Hence the Data Cleaning process is performed successfully on the given data using python code.
