

[リンク](https://drive.google.com/file/d/1GAG-efus6RF-ndmJkE6k85kIlzSME7rr/view)

## Basics

### data import/export

```

pd.read_csv(filename)
pd.read_table(filename)
pd.read_excel(filename)
pd.read_sql(query, connection_object)
pd.read_json(json_string)
pd.read_html(url)
pd.read_clipboard()
pd.DataFrame(dict)

df.to_csv(filename)
df.to_excel(filename)
df.to_sql(table_name, connection_object)
df.to_json(filename)
df.to_html(filename)
df.to_clipboard()
```

### data explore

```
df = pd.read_csv('...')

df.shape()
df.head(n)
df.tail(n)
df.info()
df.describe()
s.value_counts(dropna=False)
df.apply(pd.Series.value_counts)
df.describe()
df.mean()
df.corr()
df.count()
df.max()
df.min()
df.median()
df.std()
```

### data selection

- locとilocは範囲を指定して複数のデータを選択できる。

- locは行名と列名で位置を指定、ilocは行番号と列番号で位置を指定する。

```
df[col]
df[[col1, col2]]
s.iloc[0]
s.loc[0]
df.loc['Bob', 'age']
df.iloc[0,:]
df.iloc[0,0]
```

### data cleaning

```
df.columns = ['a','b','c']
pd.isnull()
pd.notnull()
df.dropna()
df.dropna(axis=1)
df.dropna(axis=1,thresh=n)
df.fillna(x)
s.fillna(s.mean())
s.astype(float)
s.replace(1,'one')
s.replace([1,3],['one','three'])
df.rename(columns=lambda x: x + 1)
df.rename(columns={'old_name': 'new_ name'})
df.set_index('column_one')
df.rename(index=lambda x: x + 1)
```

### filter sort groupby

```
df[df[col] > 0.5]
df[(df[col] > 0.5) & (df[col] < 0.7)]
df.sort_values(col1)
df.sort_values(col2,ascending=False)
df.sort_values([col1,col2], ascending=[True,False])
df.groupby(col)
df.groupby([col1,col2])
df.groupby(col1)[col2].mean()
df.pivot_table(index=col1, values= col2,col3], aggfunc=mean)
df.groupby(col1).agg(np.mean)
df.apply(np.mean)
df.apply(np.max, axis=1)
```

### join and concat

```
df1.append(df2)
pd.concat([df1, df2],axis=1)
df1.join(df2,on=col1,how='inner')
```

## 機械学習

### libraries

```
from sklearn.model_selection import train_test_split
from sklearn import preprocessing
from sklearn.ensemble import RandomForestRegressor
from sklearn.pipeline import make_pipeline
from sklearn.model_selection import GridSearchCV
from sklearn.neighbors import KNeighborsClassifier
from sklearn.svm import LinearSVC
from sklearn.ensemble import GradientBoostingClassifier

from sklearn.metrics import mean_squared_error, r2_score
from sklearn.externals import joblib
```

## 前処理

### libraries

```
 from sklearn.preprocessing import StandardScaler
```


## 過学習対策


### train_test_split 関数

第三引数のtest_sizeは、25%にデフォルトで設定されている

```
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, random_state=0) 

```


## その他


### google driveへmount
```
from google.colab import drive
drive.mount('/content/drive')

%cd /content/drive/My Drive/kaggle/〇〇

```
