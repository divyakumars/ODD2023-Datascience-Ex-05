# Ex:05 Feature Generation
# AIM
To read the given data and perform Feature Generation process and save the data to a file.

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

# ALGORITHM
### STEP 1
Read the given Data

### STEP 2
Clean the Data Set using Data Cleaning Process

### STEP 3
Apply Feature Generation techniques to all the feature of the data set

### STEP 4
Save the data to the file

# CODE
```
DEVELOPED BY:DIVYA K
REGISTER NO:212222230035
```
### FEATURE ENCODING
```
import pandas as pd
df=pd.read_csv("/content/Encoding Data.csv")
df
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
pm=['Hot','Warm','Cold']
e1=OrdinalEncoder(categories=[pm])
e1.fit_transform(df[["ord_2"]])
df['bo2']=e1.fit_transform(df[["ord_2"]])
df
le=LabelEncoder()
dfc=df.copy()
dfc['ord_2']=le.fit_transform(dfc['ord_2'])
dfc
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
df2=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))
df2=pd.concat([df2,enc],axis=1)
df2
pd.get_dummies(df2,columns=["nom_0"])
pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
df=pd.read_csv("/content/data.csv")
df
be=BinaryEncoder()
nd=be.fit_transform(df['Ord_1'])
dfb=pd.concat([df,nd],axis=1)
dfb1=df.copy()
dfb
from category_encoders import TargetEncoder
te=TargetEncoder()
cc=df.copy()
new=te.fit_transform(X=cc["City"],y=cc["Target"])
cc=pd.concat([cc,new],axis=1)
cc
```
### FEATURE SCALING:
```
import pandas as pd
from scipy import stats
import numpy as np
df=pd.read_csv("/content/bmi.csv")
df.head()
df.dropna()
max_vals=np.max(np.abs(df[['Height','Weight']]))
max_vals
from sklearn.preprocessing import StandardScaler
sc=StandardScaler()
df1=df.copy()
df1[['Height','Weight']]=sc.fit_transform(df1[['Height','Weight']])
df1.head(10)
max_vals=np.max(np.abs(df1[['Height','Weight']]))
max_vals
min_vals=np.min(np.abs(df1[['Height','Weight']]))
min_vals
from sklearn.preprocessing import MinMaxScaler
scaler=MinMaxScaler()
df2=df.copy()
df2[['Height','Weight']]=sc.fit_transform(df2[['Height','Weight']])
df2.head(10)
df2.head()
from sklearn.preprocessing import Normalizer
sc=Normalizer()
df3=df.copy()
df3[['Height','Weight']]=sc.fit_transform(df3[['Height','Weight']])
df3
df3.head(10)
from sklearn.preprocessing import MaxAbsScaler
sc=MaxAbsScaler()
df4=df.copy()
df4[['Height','Weight']]=sc.fit_transform(df4[['Height','Weight']])
df4
from sklearn.preprocessing import RobustScaler
sc=RobustScaler()
df5=df.copy()
df5[['Height','Weight']]=sc.fit_transform(df5[['Height','Weight']])
df5
df5.head()
```
# OUTPUT:
### FEATURE ENCODING
![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/53bd8922-33b0-46c0-8a22-aa9fa8527d85)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/bf1cb7f7-c23a-4dfc-8bba-84d4b03d4410)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/abf3f0d0-0d9c-4ef8-9a87-762180c2fccd)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/1621f824-96fd-46e2-808f-59ca1cc03700)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/004763a4-c98b-43ea-a9ee-cf563768c0b5)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/9a42277d-80ca-4792-a740-465f5c540c12)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/4e17eaae-3bcd-4d4b-bde2-256728146d63)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/771ca3ec-a002-4c15-8de1-2356720475f2)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/81e1e0ec-8500-48c6-b9e2-6c1d3c3661c9)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/a7057529-6c86-4ed9-920e-b25e0d755b61)


### FEATURE SCALING:


![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/fc6eb00f-a5fc-4eb1-b196-9307ef54961d)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/bbd5b7a1-d681-4957-9ccc-dffbf5f0196b)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/c15e2346-d2de-4050-9ed4-f2e0f233f137)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/5949853a-9d6c-4769-8864-390641d000e0)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/1a7aa862-c6e3-43c4-96e7-b37dd5ef27e1)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/9f4eeb59-26bc-4fac-9c7f-353057d386b4)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/1e7b5189-502f-4a15-8d91-43d765335ba3)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/8e623e24-5175-4b63-9698-510ef657dda7)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/ab8a1fdd-0e40-49c9-a4c2-d4838a9c9e67)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/0c01341f-cad9-438f-9353-14ba4bfb66a8)

![image](https://github.com/divyakumars/ODD2023-Datascience-Ex-05/assets/119393621/8bc614ab-8f8a-4d7d-9d4c-560f24325b50)



# RESULT:
Thus the Feature Generation and Feature Scaling process is applied to the given data set.



















