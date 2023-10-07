# Ex:05 Feature Generation
## Aim


## Algorithm



## Program
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


## Result
