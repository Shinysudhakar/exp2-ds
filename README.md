# exp2-ds
AIM:
To read a given dataset and remove outliers and save a new dataframe.

ALGORITHM:
(1) Remove outliers using IQR

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

(i) Using IQR detect weight outliers and print them

(ii) Using IQR, detect height outliers and print them

PROGRAM:

import pandas as pd

import numpy as np

import seaborn as sns

import pandas as pd

from scipy import stats

df = pd.read_csv("/content/heights.csv")

sns.boxplot(data=df)

sns.scatterplot(data=df)

max =df['height'].quantile(0.90)

min =df['height'].quantile(0.15)

max

min

dq = df[((df['height']>=min)&(df['height']<=max))]

dq

low = min-1.5*iqr

high = max+1.5*iqr

dq = df[((df['height']>=min)&(df['height']<=max))]

 dq

## ZSCORE:

 import pandas as pd

import numpy as np

import seaborn as sns

import pandas as pd

from scipy import stats

data = {'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}

df = pd.DataFrame(data)

df

sns.boxplot(data=df)

z = np.abs(stats.zscore(df))

print(df[z['weight']>3])

val = [12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]

out=[]

def d_o(val):

  ts=3
  
  m=np.mean(val)
  
  sd=np.std(val)
  
  for i in val:
  
    z=(i-m)/sd
    
    if np.abs(z)>ts:
    
      out.append(i)
      
  return out

  op = d_o(val)

  op 

OUTPUT:


  ![1](https://github.com/Shinysudhakar/exp2-ds/assets/127575325/45af8f2a-efe9-4ad0-bd44-ab6640d5e050)


![2](https://github.com/Shinysudhakar/exp2-ds/assets/127575325/95ca7667-6601-4e5e-8e8c-536f29556cb5)

![3](https://github.com/Shinysudhakar/exp2-ds/assets/127575325/b6e5c8fc-7673-4c47-ac25-2581eddd45ac)

![4](https://github.com/Shinysudhakar/exp2-ds/assets/127575325/d5c127b9-ba7b-45d1-b69f-a2a8d4114b06)


