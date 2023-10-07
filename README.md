# Ex:05 Feature Generation
## Aim

To read the given data and perform  Feature Encoding & Scaling process and save the data to a file.

## Explanation

Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

## Algorithm

STEP 1
Read the given Data

STEP 2
Clean the Data Set using Data Cleaning Process

STEP 3
Apply Feature Generation techniques to all the feature of the data set

STEP 4
Save the data to the file

## Code
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
be=BinaryEncoder()
nd=be.fit_transform(df['Ord_2'])
dfb=pd.concat([df,nd],axis=1)
dfb1=df.copy()
dfb

from category_encoders import TargetEncoder
te=TargetEncoder()
cc=df.copy()
new=te.fit_transform(X=cc["City"],y=cc["Target"])
cc=pd.concat([cc,new],axis=1)
cc

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

from sklearn.preprocessing import MinMaxScaler
scaler=MinMaxScaler()
df2=df.copy()
df2[['Height','Weight']]=scaler.fit_transform(df2[['Height','Weight']])
df2.head(10)

from sklearn.preprocessing import Normalizer
scaler=Normalizer()
df3=pd.read_csv("/content/bmi.csv")
df3[['Height','Weight']]=scaler.fit_transform(df3[['Height','Weight']])
df3

from sklearn.preprocessing import MaxAbsScaler
scaler=MaxAbsScaler()
df4=pd.read_csv("/content/bmi.csv")
df4[['Height','Weight']]=scaler.fit_transform(df4[['Height','Weight']])
df4

from sklearn.preprocessing import RobustScaler
scaler=RobustScaler()
df5=pd.read_csv("/content/bmi.csv")
df5[['Height','Weight']]=scaler.fit_transform(df5[['Height','Weight']])
df5
```

## Output

## Encoding Data

<img width="227" alt="s1" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/18a8d393-b550-458b-bab0-d6cf55932690">

## Ordinal Encoder

<img width="244" alt="s2" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/101020c0-8719-40f2-82b2-4443d0668e47">

## Label Encoder

<img width="236" alt="s3" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/5f88c1dc-dea0-4422-9775-8ec6080c4725">

## OneHot Encoder

<img width="323" alt="s4" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/0902332c-c6aa-420c-ba80-0c38f1f4864b">


<img width="478" alt="s5" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/09dc9080-88aa-40d2-9dd6-cecd585db521">

## Binary Encoder

<img width="869" alt="s6" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/3e395a3a-ee96-4bec-937d-62f5ae9378fe">


<img width="503" alt="s7" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/18f6aba1-425b-4745-ae23-e862410de244">

## Target Encoder

<img width="401" alt="s8" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/7890cb6f-a16e-47d3-905b-e8b9f4b59965">


## Scaling Data

<img width="203" alt="s9" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/08a80680-3e33-4d68-a6bd-5503887e3613">


<img width="220" alt="s10" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/8b115616-bc1a-485c-b0da-780d059b4663">


<img width="871" alt="s11" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/8c8bf289-c949-4090-9950-1db120e43e2f">

## Standard Scaker

<img width="235" alt="s12" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/1d7b5296-bbe1-43a0-a25a-75522c6805fb">

## MinMax Scaler

<img width="233" alt="s13" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/770245fa-8d3c-4ebf-ad10-e33c203e6d3f">

## Normalizer

<img width="248" alt="s14" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/8ff79bc1-9d2e-4a84-bebe-15f70e402d5f">

## MaxAbs Scaler

<img width="233" alt="s15" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/9d376c40-ae43-4daa-b6b0-4011e2c3a2d5">

## Robust Scaler

<img width="261" alt="s16" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-05/assets/113674204/fac1b4af-710a-4be7-aaa6-a6e1dcb6204a">


## Result

Thus the Feature Generation and Feature Scaling process is applied to the given data set.
