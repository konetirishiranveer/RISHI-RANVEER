#Boxplot for the Fare columns
sns.boxplot(x=df['Fare'])

#Removing the outliers in Fare columns
df.drop(df[df['Fare']>300].index,inplace=True)

df['Embarked'].value_counts()

df['Embarked'].mode()

df.fillna({'Embarked':'S'},inplace=True)

df.isnull().sum()

df.select_dtypes(include='object').columns

from sklearn.preprocessing import OneHotEncoder
one = OneHotEncoder()

df['Sex'] = one.fit_transform(df[['Sex']]).toarray()

df['Embarked'] = one.fit_transform(df[['Embarked']]).toarray()

from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
df['Age'] = scaler.fit_transform(df[['Age']])
df['Fare'] = scaler.fit_transform(df[['Fare']])

df.head()

