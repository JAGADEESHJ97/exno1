NAME:JAGADEESH J
REG.NO:212223110015
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
import numpy as np
import pandas as pd
a = pd.read_csv("/SAMPLEIDS.csv")
print(a)
```
## OUTPUT:
<img width="773" height="731" alt="image" src="https://github.com/user-attachments/assets/dd381026-f201-458a-838d-6c1229206bbb" />

```
a.head(4)
```
## OUTPUT:
<img width="857" height="173" alt="image" src="https://github.com/user-attachments/assets/b547e787-e27e-4ed4-b843-9884416af76c" />

```
a.tail(5)
```
## OUTPUT:
<img width="850" height="195" alt="image" src="https://github.com/user-attachments/assets/8d8ff469-9d78-4309-9919-d2e3f3d7acae" />

```
a.isnull()
```
## OUTPUT:
<img width="869" height="736" alt="image" src="https://github.com/user-attachments/assets/41b5cffa-dfa1-4df5-af1f-98577795ed54" />

```
a.notnull()
```
## OUTPUT:
<img width="869" height="740" alt="image" src="https://github.com/user-attachments/assets/07c945a0-3d9d-4334-b3e6-d760f8ee4a97" />

```
a.isnull().sum()
```
## OUTPUT:
<img width="197" height="485" alt="image" src="https://github.com/user-attachments/assets/59899acb-07df-427f-b510-7c282cce5e54" />

```
a.isnull().any()
```
## OUTPUT:
<img width="161" height="482" alt="image" src="https://github.com/user-attachments/assets/8245b4e0-c13a-4027-b7d0-4076b8667932" />

```
a.dropna(axis=1)
```
## OUTPUT:
<img width="291" height="733" alt="image" src="https://github.com/user-attachments/assets/1c76129b-8334-4791-bb92-942be4c8722a" />

```
a.dropna(axis=0)
```
## OUTPUT:
<img width="878" height="477" alt="image" src="https://github.com/user-attachments/assets/e0d955da-68b6-46b8-807b-ce2d5d34bf86" />

```
a.fillna(0)
```
## OUTPUT:
<img width="966" height="732" alt="image" src="https://github.com/user-attachments/assets/6f1f3c00-3963-4fd1-a823-038187e114f4" />

```
a.fillna(method="ffill")
```
## OUTPUT:
<img width="1361" height="781" alt="image" src="https://github.com/user-attachments/assets/8183e9da-21ea-428a-9c6d-2889df50c990" />


```
a.bfill()
```
## OUTPUT:
<img width="917" height="738" alt="image" src="https://github.com/user-attachments/assets/e251d361-529d-4b29-9c3a-1127cf8fc24c" />

```
a.fillna({'REGNO':0, 'NAME':'PRAVEEN'})
```
## OUTPUT:
<img width="981" height="742" alt="image" src="https://github.com/user-attachments/assets/86be7234-561e-4e55-b94e-274570c95aef" />

```
b=pd.read_csv("/content/drive/MyDrive/iris.csv")
print(b)
```
## OUTPUT:
<img width="572" height="305" alt="image" src="https://github.com/user-attachments/assets/fb0e84d7-6fd9-4c65-8d86-c58a0ca99ea6" />

```
b.describe()
```
## OUTPUT:
<img width="520" height="334" alt="image" src="https://github.com/user-attachments/assets/36754de0-d18e-4089-a472-508ba450f3e8" />

```
import seaborn as sns
sns.boxplot(x="sepal_width",data=b)
```
## OUTPUT:
<img width="562" height="505" alt="image" src="https://github.com/user-attachments/assets/063d3831-6b44-44a1-82de-4e687b0d675c" />

```
 q1=ir.sepal_width.quantile(0.25)
 q3=ir.sepal_width.quantile(0.75)
 iqr=q3-q1
 print(iqr)
```
## OUTPUT:
<img width="291" height="126" alt="image" src="https://github.com/user-attachments/assets/df7e1692-d0c3-4b60-8a61-ad1e30266fcd" />

```
rid=b[((b.sepal_width<(q1-1.5*iqr))|(b.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```
## OUTPUT:
<img width="578" height="254" alt="image" src="https://github.com/user-attachments/assets/2f72cf5a-3af1-4185-bf82-e03dd249e7e1" />

```
rid=b[~((ir.sepal_width<(q1-1.5*iqr))|(b.sepal_width>(q3+1.5*iqr)))]
rid
```
## OUTPUT:
<img width="590" height="462" alt="image" src="https://github.com/user-attachments/assets/96f324c6-a19c-4701-889e-61b1e75cacd9" />

```
rid=b[((b.sepal_width>(q1-1.5*iqr))&(b.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']
```
## OUTPUT:
<img width="677" height="493" alt="image" src="https://github.com/user-attachments/assets/91891a8e-8e57-45a7-983d-f49ec8f73f3e" />

```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(b.sepal_width))
z
```
## OUTPUT:
<img width="679" height="617" alt="image" src="https://github.com/user-attachments/assets/8f19f00e-e734-4bcc-9aad-7f12b22cb4c3" />


# Result:
 Thus the programs are executed successfully.
