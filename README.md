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
import matplotlib.pyplot as plt
data = pd.read_csv("/content/SAMPLEIDS.csv")
data.head()
```
![Screenshot 2024-02-27 153848](https://github.com/Anusharonselva/exno1/assets/119405600/bfa08d6a-3477-4717-be50-aefb73b45285)
```
df.head(10)
```
![Screenshot 2024-02-27 154918](https://github.com/Anusharonselva/exno1/assets/119405600/150ae542-c589-41a1-9e49-7c87a4538732)
```
df.tail(10)
```
![Screenshot 2024-02-27 155025](https://github.com/Anusharonselva/exno1/assets/119405600/e64fb63a-0a08-467f-8ef2-ec0ca3abc842)
```
df.info()
```
![Screenshot 2024-02-27 155130](https://github.com/Anusharonselva/exno1/assets/119405600/9d11c8a1-7812-43ab-998c-34df3c1a0996)
```
df.describe()
```
![Screenshot 2024-02-27 155233](https://github.com/Anusharonselva/exno1/assets/119405600/13c06dfd-ea8f-4430-8b02-7a010c09e3e7)
```
df.shape
```
![Screenshot 2024-02-27 155310](https://github.com/Anusharonselva/exno1/assets/119405600/ea72c490-2acf-44c2-a1d9-c248efccdbf9)
```
df.isnull().sum()
```
![Screenshot 2024-02-27 155352](https://github.com/Anusharonselva/exno1/assets/119405600/4b0dec01-846c-40cd-a4f7-3c53c1e37247)
```
df.nunique()
```
![Screenshot 2024-02-27 155443](https://github.com/Anusharonselva/exno1/assets/119405600/3bb286a9-6dca-4ccc-89c3-e10e40c71bca)
```
df['GENDER'].value_counts()
```
![Screenshot 2024-02-27 155522](https://github.com/Anusharonselva/exno1/assets/119405600/3266705c-0c98-4679-b353-c86fcca9acf4)
```
mn=df.TOTAL.mean()
mn
```
![Screenshot 2024-02-27 155622](https://github.com/Anusharonselva/exno1/assets/119405600/994ed32a-0230-48dd-86de-e50eac4b5ade)
```
df.TOTAL.fillna(mn,inplace=True)
df.M4.fillna(0)
```
![Screenshot 2024-02-27 155953](https://github.com/Anusharonselva/exno1/assets/119405600/877f8c91-5de3-448f-8e7e-36d3fd406385)
```
min=df.M4.min()
min
```
![Screenshot 2024-02-27 160229](https://github.com/Anusharonselva/exno1/assets/119405600/f8a6e719-531d-40ee-8ef6-dcf65e665282)
```
df.M4.fillna(min,inplace=True)
df
```
![Screenshot 2024-02-27 160505](https://github.com/Anusharonselva/exno1/assets/119405600/bdfb0174-7c17-42a1-a384-25d3f032fc73)
```
df.isnull()
```
![Screenshot 2024-02-27 160853](https://github.com/Anusharonselva/exno1/assets/119405600/adfbb765-5331-4b59-991e-7688bd4cdcd0)
```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![Screenshot 2024-02-27 161049](https://github.com/Anusharonselva/exno1/assets/119405600/51139c49-58f1-463d-870a-ca4b0097e345)
```
sns.boxplot(data=af)
```
![Screenshot 2024-02-27 161158](https://github.com/Anusharonselva/exno1/assets/119405600/79655949-4ba6-40f5-8752-22695fc9bc2d)
```
sns.scatterplot(data=af)
```
![Screenshot 2024-02-27 161258](https://github.com/Anusharonselva/exno1/assets/119405600/2b88da83-002b-4a93-b5d0-db655e1f0d7c)
```
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
```
![Screenshot 2024-02-27 161348](https://github.com/Anusharonselva/exno1/assets/119405600/355d17f3-35f6-49b8-961b-32d9c170545c)
```
low=q1-1.5*iqr
low
```
![Screenshot 2024-02-27 161428](https://github.com/Anusharonselva/exno1/assets/119405600/d91ed0f6-f89b-4171-94a8-fa2571c1d36f)
```
high=q3+1.5*iqr
high
```
![Screenshot 2024-02-27 161455](https://github.com/Anusharonselva/exno1/assets/119405600/b1965b19-68d8-4653-b662-46caf6658d63)
```
af=af[((af>=low)&(af<=high))]
af
```
![Screenshot 2024-02-27 161545](https://github.com/Anusharonselva/exno1/assets/119405600/3bfd062a-7bd6-495c-81e6-78c88749788e)
```
af.dropna()
```
![Screenshot 2024-02-27 161623](https://github.com/Anusharonselva/exno1/assets/119405600/ffd1abe8-b84e-4c13-bab4-e61366c2722d)
```
sns.boxplot(data=af)
```
![Screenshot 2024-02-27 161749](https://github.com/Anusharonselva/exno1/assets/119405600/dd248634-5228-4fae-9649-ab633761e084)
```
data=[1,12,15,18,21,24,27,20,30,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,158]
df=pd.DataFrame(data)
df
```
![Screenshot 2024-02-27 165123](https://github.com/Anusharonselva/exno1/assets/119405600/465d8282-cd30-407e-a324-a2c47a1e931e)
```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![Screenshot 2024-02-27 165355](https://github.com/Anusharonselva/exno1/assets/119405600/b5f74efa-cb34-4a51-88f3-b9f2e952398c)

# Result
Thus we read the given data and perform data cleaning and save the cleaned data to a file.
