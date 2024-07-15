```markdown
# Jupyter Notebook Document

This Jupyter Notebook document contains multiple cells with code and markdown content. Each cell can be executed independently.

## Cells in this Jupyter Notebook

### Cell 0
```python
import pandas as pd 
import seaborn as sns
```

### Cell 1
```python
tips = sns.load_dataset('tips') 
```

### Cell 2
```python
tips
```

### Cell 3
```python
tips.head()
```

### Cell 4
```python
titanic = pd.read_csv('train 1.csv')
```

### Cell 5
```python
iris = sns.load_dataset('iris')
```

### Cell 6
```python
iris
```

### Cell 7
```markdown
1. Scatterplot(Numerical - Numerical)
```

### Cell 8
```python
sns.scatterplot(data=tips, x='total_bill', y='tip', hue='sex',style='smoker',size = 'size')
```

### Cell 9
```markdown
#BAR Plot (Numerical - Categorical)
```

### Cell 10
```python
titanic.head()  
```

### Cell 11
```python
sns.barplot(x=titanic['Pclass'], y=titanic['Age'])
```

### Cell 12
```python
sns.barplot(x=titanic['Pclass'], y=titanic['Fare'])
```

### Cell 13
```python
sns.barplot(x='Pclass', y='Fare', hue='Sex', data=titanic)
```

### Cell 14
```python
sns.barplot(x='Pclass', y='Age', hue='Sex', data=titanic)
```

### Cell 15
```markdown
BOX Plot (Numerical(y-axis)-Categorical(x-axis))
```

### Cell 16
```python
sns.boxplot(x='Sex',y='Age',data=titanic)
```

### Cell 17
```python
sns.boxplot(x='Sex',y='Age',data=titanic,hue='Survived')
```

### Cell 18
```markdown
Distplot(Numerical-Categorical)
```

### Cell 19
```python
sns.displot(x ='Age',data=titanic)
```

### Cell 20
```python
sns.displot(titanic['Age'])
```

### Cell 21
```python
sns.displot(x='Age',data=titanic[titanic['Survived']==0])
```

### Cell 22
```python
#Alternative code for the above situation 
sns.displot(titanic[titanic['Survived']==0]['Age'])
sns.displot(x='Age',data=titanic[titanic['Survived']==1])
```

### Cell 23
```python
sns.displot(titanic[titanic['Survived']==0]['Age'])
sns.displot(titanic[titanic['Survived']==1]['Age'])
```

### Cell 24
```python
sns.displot(x='Age',data=titanic[titanic['Survived']==1])
```

### Cell 25
```python
sns.displot(x='Age',data=titanic[titanic['Survived']==1])
sns.displot(x='Age',data=titanic[titanic['Survived']==0])
```

### Cell 26
```python
sns.displot(x='Age',data=titanic[titanic['Survived']==1],hist  = False)
sns.displot(x='Age',data=titanic[titanic['Survived']==0],hist = False)
```

### Cell 27
```markdown
#Hist Function has been deprecated in Seaborn
```

### Cell 28
```python
sns.displot(x='Age', data=titanic[titanic['Survived']==1])
sns.displot(x='Age', data=titanic[titanic['Survived']==0])
```

### Cell 29
```markdown
5. Heatmap(Categorical - Categorical)
```

### Cell 30
```python
titanic.head(3)
```

### Cell 31
```python
pd.crosstab(titanic['Pclass'],titanic['Survived'])
```

### Cell 32
```python
sns.heatmap(pd.crosstab(titanic['Pclass'],titanic['Survived']))
```

### Cell 33
```python
titanic.groupby('Pclass')['Survived'].mean()
```

### Cell 34
```python
titanic.groupby('Pclass')['Survived'].mean()*100
```

### Cell 35
```python
(titanic.groupby('Pclass')['Survived'].mean()*100).plot(kind='bar',color = 'yellow')
```

### Cell 36
```python
(titanic.groupby('Sex')['Survived'].mean()*100)
```

### Cell 37
```python
(titanic.groupby('Embarked')['Survived'].mean())*100
```

### Cell 38
```markdown
Cluster Map (Categorical - Categorical)
```

### Cell 39
```python
pd.crosstab(titanic['SibSp'],titanic['Survived'])
```

### Cell 40
```python
sns.clustermap(pd.crosstab(titanic['SibSp'],titanic['Survived']))
```

### Cell 41
```python
sns.clustermap(pd.crosstab(titanic['Parch'],titanic['Survived']))
```

### Cell 42
```markdown
#Pairplot
```

### Cell 43
```python
iris.head()
```

### Cell 44
```python
sns.pairplot(iris)
```

### Cell 45
```python
sns.pairplot(iris,hue='species')
```

### Cell 46
```markdown
Lineplot (Numerical - Numerical)
```

### Cell 47
```python
flights = sns.load_dataset('flights')
```

### Cell 48
```python
flights.head()
```

### Cell 49
```python
flights.groupby('month')['passengers'].sum()
```

### Cell 50
```python
phew = flights.groupby('year')['passengers'].sum().reset_index()
```

### Cell 51
```python
sns.lineplot(x='year',y='passengers',data=phew)
```

### Cell 52
```python
flights
```

### Cell 53
```python
flights.pivot_table(index='month',columns='year',values='passengers')
```

### Cell 54
```python
sns.heatmap(flights.pivot_table(index='month',columns='year',values='passengers'))
```

### Cell 55
```python
sns.clustermap(flights.pivot_table(index='month',columns='year',values='passengers'))
```

### Cell 56
This is a markdown cell. Markdown cell is used to describe and document your workflow.

### Cell 57
```python

```

## Variables in this Jupyter Notebook

### Variable: flights
Type: pandas.core.frame.DataFrame
Value:
```
    year month  passengers
0    1949   Jan         112
1    1949   Feb         118
2    1949   Mar         132
3    1949   Apr         129
4    1949   May         121
..    ...   ...         ...
139  1960   Aug         606
140  1960   Sep         508
141  1960   Oct         461
142  1960   Nov         390
143  1960   Dec         432

[144 rows x 3 columns]
```
Summary:
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 144 entries, 0 to 143
Data columns (total 3 columns):
 #   Column      Non-Null Count  Dtype   
---  ------      --------------  -----   
 0   year        144 non-null    int32   
 1   month       144 non-null    category
 2   passengers  144 non-null    int32   
dtypes: category(1), int32(2)
memory usage: 1.8 KB
```

### Variable: iris
Type: pandas.core.frame.DataFrame
Value:
```
     sepal_length  sepal_width  petal_length  petal_width    species
0             5.1          3.5           1.4          0.2     setosa
1             4.9          3.0           1.4          0.2     setosa
2             4.7          3.2           1.3          0.2     setosa
3             4.6          3.1           1.5          0.2     setosa
4             5.0          3.6           1.4          0.2     setosa
..            ...          ...           ...          ...        ...
145           6.7          3.0           5.2          2.3  virginica
146           6.3          2.5           5.0          1.9  virginica
147           6.5          3.0           5.2          2.0  virginica
148           6.2          3.4           5.4          2.3  virginica
149           5.9          3.0           5.1          1.8  virginica

[150 rows x 5 columns]
```
Summary:
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 150 entries, 0 to 149
Data columns (total 5 columns):
 #   Column        Non-Null Count  Dtype  
---  ------        --------------  -----  
 0   sepal_length  150 non-null    float64
 1   sepal_width   150 non-null    float64
 2   petal_length  150 non-null    float64
 3   petal_width   150 non-null    float64
 4   species       150 non-null    object 
dtypes: float64(4), object(1)
memory usage: 6.0+ KB
```

### Variable: phew
Type: pandas.core.frame.DataFrame
Value:
```
    year  passengers
0   1949        1520
1   1950        1676
2   1951        2042
3   1952        2364
4   1953        2700
5   1954        2867
6   1955        3408
7   1956        3939
8   1957        4421
9   1958        4572
10  1959        5140
11  1960        5714
```
Summary:
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 12 entries, 0 to 11
Data columns (total 2 columns):
 #   Column      Non-Null Count  Dtype
---  ------      --------------  -----
 0   year        12 non-null     int32
 1   passengers  12 non-null     int32
dtypes: int32(2)
memory usage: 228.0 bytes
```

### Variable: tips
Type: pandas.core.frame.DataFrame
Value:
```
     total_bill   tip     sex smoker   day    time  size
0         16.99  1.01  Female     No   Sun  Dinner     2
1         10.34  1.66    Male     No   Sun  Dinner     3
2         21.01  3.50    Male     No   Sun  Dinner     3
3         23.68  3.31    Male     No   Sun  Dinner     2
4         24.59  3.61  Female     No   Sun  Dinner     4
..          ...   ...     ...    ...   ...     ...   ...
239       29.03  5.92    Male     No   Sat  Dinner     3
240       27.18  2.00  Female    Yes   Sat  Dinner     2
241       22.67  2.00    Male    Yes   Sat  Dinner     2
242       17.82  1.75    Male     No   Sat  Dinner     2
243       18.78  3.00  Female     No  Thur  Dinner     2

[244 rows x 7 columns]
```
Summary:
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 244 entries, 0 to 243
Data columns (total 7 columns):
 #   Column      Non-Null Count  Dtype   
---  ------      --------------  -----   
 0   total_bill  244 non-null    float64 
 1   tip         244 non-null    float64 
 2   sex         244 non-null    category
 3   smoker      244 non-null    category
 4   day         244 non-null    category
 5   time        244 non-null    category
 6   size        244 non-null    int64   
dtypes: category(4), float64(2), int64(1)
memory usage: 7.4 KB
```

### Variable: titanic
Type: pandas.core.frame.DataFrame
Value:
```
     PassengerId  Survived  Pclass                                               Name     Sex   Age  SibSp  Parch            Ticket     Fare Cabin Embarked
0              1         0       3                            Braund, Mr. Owen Harris    male  22.0      1      0         A/5 21171   7.2500   NaN        S
1              2         1       1  Cumings, Mrs. John Bradley (Florence Briggs Th...  female  38.0      1      0          PC 17599  71.2833   C85        C
2              3         1       3                             Heikkinen, Miss. Laina  female  26.0      0      0  STON/O2. 3101282   7.9250   NaN        S
3              4         1       1       Futrelle, Mrs. Jacques Heath (Lily May Peel)  female  35.0      1      0            113803  53.1000  C123        S
4              5         0       3                           Allen, Mr. William Henry    male  35.0      0      0            373450   8.0500   NaN        S
..           ...       ...     ...                             ...

Summary:
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 891 entries, 0 to 890
Data columns (total 12 columns):
 #   Column       Non-Null Count  Dtype  
---  ------       --------------  -----  
 0   PassengerId  891 non-null    int64  
 1   Survived     891 non-null    int64  
 2   Pclass       891 non-null    int64  
 3   Name         891 non-null    object 
 4   Sex          891 non-null    object 
 5   Age          714 non-null    float64
 6   SibSp        891 non-null    int64  
 7   Parch        891 non-null    int64  
 8   Ticket       891 non-null    object 
 9   Fare         891 non-null    float64
 10  Cabin        204 non-null    object 
 11  Embarked     889 non-null    object 
dtypes: float64(2), int64(5), object(5)
memory usage: 83.7+ KB
```
```