# Feature-Generation

# AIM:
To read the given data and perform Feature Generation process and save 
the data to a file.

# EXPLANATION:
Feature Generation (also known as feature construction, feature 
extraction or feature engineering) is the process of transforming features into 
new features that better relate to the target.

# ALGORITHM:
STEP-1:

 Read the given Data.

STEP-2:

Clean the Data Set using Data Cleaning Process.

STEP-3:

Apply Feature Generation techniques to all the feature of the data set.

STEP-4:
 
 Save the data to the file.

# CODE:
# ORDINAL ENCODER:
```
import pandas as pd
import seaborn as sns
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
df = pd.read_excel("Workshop_feature Engg.csv.xlsx")
carbody=['convertible','wagon','hatchback','sedan','hardtop']
enc=OrdinalEncoder(categories=[carbody])
enc.fit_transform(df[['carbody']])
df['Carbody']=enc.fit_transform(df[['carbody']])
df
fuelsystem=['mpfi','mfi','1bbl','2bbl','idi']
enc=OrdinalEncoder(categories=[fuelsystem])
enc.fit_transform(df[['fuelsystem']])
df['Fuelsystem']=enc.fit_transform(df[['fuelsystem']])
df
enginetype=['dohc','ohc','ohcv']
enc=OrdinalEncoder(categories=[enginetype])
enc.fit_transform(df[['enginetype']])
df['Enginetype']=enc.fit_transform(df[['enginetype']])
df
```
# LABEL ENCODER:
```
import pandas as pd
import seaborn as sns
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
from google.colab import files
uploaded = files.upload()
df = pd.read_excel("Workshop_feature Engg.csv.xlsx")
le=LabelEncoder()
df['Carname']=le.fit_transform(df['CarName'])
df
le=LabelEncoder()
df['Carbody']=le.fit_transform(df['carbody'])
df
le=LabelEncoder()
df['CarID']=le.fit_transform(df['car_ID'])
df
le=LabelEncoder()
df['Carwidth']=le.fit_transform(df['carwidth'])
df
le=LabelEncoder()
df['Enginesize']=le.fit_transform(df['enginesize'])
df
```
# ONE HOT ENCODER:
```
import pandas as pd
import seaborn as sns
from sklearn.preprocessing import OneHotEncoder
from google.colab import files
uploaded = files.upload()
df = pd.read_excel("Workshop_feature Engg.csv.xlsx")
ohe=OneHotEncoder(sparse=False)
enc=pd.DataFrame(ohe.fit_transform(df[['enginetype']]))
df=pd.concat([df,enc],axis=1)
df
ohe=OneHotEncoder(sparse=False)
enc=pd.DataFrame(ohe.fit_transform(df[['fuelsystem']]))
df=pd.concat([df,enc],axis=1)
df
ohe=OneHotEncoder(sparse=False)
enc=pd.DataFrame(ohe.fit_transform(df[['carbody']]))
df=pd.concat([df,enc],axis=1)
df
```
# BINARY ENCODER:
```
import pandas as pd
import seaborn as sns
!pip install category_encoders
from category_encoders import BinaryEncoder
from google.colab import files
uploaded = files.upload()
df = pd.read_excel("Workshop_feature Engg.csv.xlsx")
be=BinaryEncoder()
newdata=be.fit_transform(df['drivewheel'])
df1=pd.concat([df,newdata],axis=1)
df1
be=BinaryEncoder()
newdata=be.fit_transform(df['fueltype'])
df1=pd.concat([df,newdata],axis=1)
df1
be=BinaryEncoder()
newdata=be.fit_transform(df['aspiration'])
df1=pd.concat([df,newdata],axis=1)
df1
be=BinaryEncoder()
newdata=be.fit_transform(df['doornumber'])
df1=pd.concat([df,newdata],axis=1)
df1
be=BinaryEncoder()
newdata=be.fit_transform(df['drivewheel'])
df1=pd.concat([df,newdata],axis=1)
df1
```
