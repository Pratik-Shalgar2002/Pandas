# Pandas In Python
## Data Analysis
: Data analysis is a process of inspecting, cleaning, transforming and modelling data with goal of discoring useful information, informing conclusions and supporting decision making. 

## What is Pandas ?
- Name pandas refere to the "Panel Data" and " Python Data Analysis" by Mckinney in 2008.
- Used for working data sets.
- has functions for analyzing, cleaning, exploring and manipulating data.
- read and write data structure and different format such as CSV, JSON, XML, etc.

## Pandas Data Structures
- series : One Dimentional labeled arrays (pd.series).
- DataFrame : Two Dimentional Data Structure with columns much like table.
- panel : a panel is a 3D container of data.

## Installations
```
pip install pandas
```

## Import
```
import pandas as pd
```

## Imporatance of Pandas

- **Data Structures**: Provides DataFrame and Series for easy data handling.
- **Data Cleaning**: Simplifies data cleaning and transformation.
- **User-Friendly**: Intuitive syntax, easy for beginners.
- **Integration**: Works well with NumPy, Matplotlib, etc.
- **Data Analysis**: Supports descriptive statistics, grouping, and aggregation.
- **Data Import/Export**: Reads and writes data in various formats (CSV, Excel, SQL).


## Data Structure in Python Pandas
- The Pandas provides two data structure for peocessing data
- Series & DataFrame and panel

## Series
- It is defined as one dimensional array that is capable at storing various data type..
```
import pandas as pd
x = [1,2,3,4]
var = pd.Series(x)
print(var)
print(var.dtype)
print(type(var))
import pandas as pd
x = [1,2,3,4]
var = pd.Series(x, index = ["a","b","c","d"])
print(var)
print(type(var))
import pandas as pd
x = [1,2,3,4]
var = pd.Series(x, index = ["a","b","c","d"],dtype="float", name = "Python")
print(var)
print(type(var))
```
```

import pandas as pd

my_dict = {
    "name": "Alice",
    "age": 25,
    "city": "New York",
    "occupation": "Engineer",
    "hobbies": ["reading", "cycling", "traveling"],
    "skills": {"Python": "advanced", "SQL": "intermediate", "Machine Learning": "beginner"},
    "married": False,
    "pets": None
}
var = pd.Series(my_dict)
print(var)
print(type(var))
# When you have mix data dtype returns Object

s = pd.Series(12)
print(s)
s = pd.Series(12, index = [1,2,3,4])
print(s)
s = pd.Series(12, index = [1,2,3,4,5,6,7,8])
d = pd.Series(12, index = [1,2,3,4])
print(s + d)
# Unlike Numpy Trowing error it returns NaN value 
```

## DataFrame
- **Definition**: A DataFrame is a 2-dimensional, size-mutable, and labeled data structure in Pandas, similar to a table in a spreadsheet or a SQL database.
### List
```
import pandas as pd
a = [1,2,3,4]
var = pd.DataFrame(a)
print(var)
print(type(var))
import pandas as pd
a = [1,2,3,4]
var = pd.DataFrame(a, index=['a','s','d','f'], columns = [1])
print(var)
print(type(var))
import pandas as pd
a = [[1,2,3,4],[1,2,3,4]]
var = pd.DataFrame(a, columns = [1,2,3,4])
print(var)
print(type(var))
```

### Dict
```
import pandas as pd
s = {'a':[1,2,3,4],'b':[1,2,3,4],'c':[1,2,3,4],'d':[1,2,3,4]}
var= pd.DataFrame(s)
print(var)
print(type(var))
- All array must be same length
import pandas as pd
s = {'a':[1,2,3,4],'b':[1,2,3,4],'c':[1,2,3,4],'d':[1,2,3,4]}
var= pd.DataFrame(s, columns = ['a'])
print(var)
print(type(var))
import pandas as pd
s = {'a':[1,2,3,4],'b':[1,2,3,4],'c':[1,2,3,4],'d':[1,2,3,4]}
var= pd.DataFrame(s, columns =['a','d'])
print(var)
print(type(var))
import pandas as pd
s = {'a':[1,2,3,4],'b':[1,2,3,4],'c':[1,2,3,4],'d':[1,2,3,4]}
var= pd.DataFrame(s,index = ['a','b','c','d'])
print(var)
print(type(var))
```
### Series
```
import pandas as pd
a = {"a":pd.Series([1,2,3,4]),"b":pd.Series([1,2,3,4])}
var = pd.DataFrame(a)
print(var)
print(type(var))
```
## Arthmetic Operations
```
import pandas as pd
a = pd.DataFrame({"A":[1,2,3,4],"B":[11,12,14,15]})
a
a["C"] = a["A"]+a["B"]
a

a["C"] = a["A"]-a["B"]
a
a["C"] = a["A"]*a["B"]
a
a["C"] = a["A"]/a["B"]
a
a["C"] = a["A"]%a["B"]
a
a["Group_1"] = a["A"] < 10 
a["Group_2"] = a["B"] < 10 
a
a["Group_1"] = a["A"] <= 10 
a["Group_2"] = a["B"] <= 10 
a
a["Group_1"] = a["A"] > 10 
a["Group_2"] = a["B"] > 10 
a
a["Group_1"] = a["A"] >= 10 
a["Group_2"] = a["B"] >= 10 
a
a["Group_1"] = a["A"] == 10 
a["Group_2"] = a["B"] == 10 
a
a["Group_1"] = a["A"] != 10 
a["Group_2"] = a["B"] != 10 
a
```
## Delete and Insert Functions
### Insert
```
import pandas as pd
x = pd.DataFrame({'A':[1,2,3,4,5],'B':[6,7,8,9,10]})
x
x.insert(1,'New_1',x['A'])
x
x.insert(2,'New_2',[11,12,14,14,15])
x
import pandas as pd
x = pd.DataFrame({'A':[1,2,3,4,5],'B':[6,7,8,9,10]})
x

x = pd.DataFrame({'A':[1,2,3,4,5],'B':[6,7,8,9,10]})
x['C']= x['A'][:3]
x
```
### Delete
```
import pandas as pd
x = pd.DataFrame({'A':[1,2,3,4,5],'B':[6,7,8,9,10],'C':[11,12,14,15,13]})
x
y = x.pop("B")
y
x
import pandas as pd
x = pd.DataFrame({'A':[1,2,3,4,5],'B':[6,7,8,9,10],'C':[11,12,14,15,13]})
x
del x["A"]

x
```

## Write CSV file in Python Pandas

**CSV VS XLS**

- CSV format is plain text format which are seperated by commas.
- XLS format is an excel sheets binary file format which holds informations abour all the worksheets in file including content and formating.
```
import pandas as pd
x = pd.DataFrame({'A':[1,2,3,4],'B':[5,6,7,8],'C':[11,12,13,14]})
x
x.to_csv("File_1")
x.to_csv("File_2", index =False)
x.to_csv("File_3", index =False, header=[1,2,3])
```
## Read CSV File
```
import pandas as pd
```
#### 1
```
x = pd.read_csv("D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv")
x
```
#### 2
```
x = pd.read_csv("D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv", nrows = 5)
x
```
#### 3
```
x = pd.read_csv("D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv", usecols = ['job_title'])
x
x = pd.read_csv("D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv", usecols = [3])
x
x = pd.read_csv("D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv", usecols = [0,4])
x
```
#### 4
```
x = pd.read_csv("D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv",skiprows= [0])
x
```
#### 5
```
x = pd.read_csv("D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv", index_col = "job_title")
x
```
#### 6
```
x = pd.read_csv("D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv", header = 2)
x
```

#### 7
```
x = pd.read_csv("D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv", names=["new"])
x
```
#### 8
```
x = pd.read_csv("D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv", header = None , prefix="col")
x
```
#### 9


## Pandas Function
```
import pandas as pd

csv = pd.read_csv("D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv")
csv
# Index
a = csv.index
print(a)
#Columns
a = csv.columns
print(a)
# Describe
a = csv.describe()
print(a)

# Head
csv.head()
csv.head(3)
# Tail
csv.tail()
csv.tail(2)
# Slicing
a = csv[6:11]
a
# Type
print(type(csv))
# Index Array
csv.index.array
# convert index num into array
# Numpy Array
csv.to_numpy()
# As Array
import numpy as np
a = np.asarray(csv)
a
# Sort Index
a = csv.sort_index(axis= 0,ascending= False)
a
b = csv.sort_index(axis= 1,ascending= False)
b
#  Adding Data
csv["job_title_short"][2] = "Pandas"
csv
# Loc
csv.loc[0,"job_title_short"] = "python pandas"
csv
import pandas as pd

csv2 = pd.read_csv( "D:\\Study\\Python Data Analysis\\Pandas\\Job_posting.csv")

csv2

# Iloc
csv2.iloc[2,2]
# Drop
csv2.drop('job_title',axis = 1)
csv2.drop(2,axis = 0)
```

## Handing Missing Value
### Replace
```
import pandas as pd


df = pd.DataFrame({'A': [1, 2, 3, 4], 'B': [5, 6, 7, 8]})
# Replace 1 with 100 in column 'A'
df_replaced = df.replace({1: 100})
print(df_replaced)
```

### interpolate
```

df = pd.DataFrame({'A': [1, None, 3, None], 'B': [5, 6, None, 8]})
# Interpolate missing values (linear method by default)
df_interpolated = df.interpolate()
print(df_interpolated)
```
## fillna
```
df = pd.DataFrame({'A': [1, None, 3, None], 'B': [5, 6, None, 8]})

# Fill missing values with 0
df_filled = df.fillna(0)
print(df_filled)

# Fill missing values using forward fill
df_filled_ffill = df.fillna(method='ffill')
print(df_filled_ffill)
```

## dropna
```
df = pd.DataFrame({'A': [1, None, 3, None], 'B': [5, 6, None, 8]})

# Drop rows with missing values
df_dropped = df.dropna()
print(df_dropped)

# Drop columns with missing values
df_dropped_columns = df.dropna(axis=1)
print(df_dropped_columns)
```
## Marge
```
import pandas as pd

n1 = pd.DataFrame({'A':[1,2,3,4],'B':[1,2,3,4]})
print(n1)
print()
n2 = pd.DataFrame({'A':[1,2,3,4],'C':[1,2,3,4]})
print(n2)

pd.merge(n1,n2,on= 'A')
n1 = pd.DataFrame({'A':[1,2,3,4],'B':[1,2,3,4]})
n2 = pd.DataFrame({'A':[1,2,3,5],'C':[1,2,3,4]})
pd.merge(n1,n2,how='inner')
pd.merge(n1,n2,how='outer')
pd.merge(n1,n2,how='left')
pd.merge(n1,n2,how='right')
pd.merge(n1,n2,how='right', indicator = True)
n1 = pd.DataFrame({'A':[1,2,3,4],'B':[1,2,3,4]})
n2 = pd.DataFrame({'A':[1,2,3,5],'B':[1,2,3,4]})
pd.merge(n1,n2)
pd.merge(n1,n2,left_index=True,right_index =True)
pd.merge(n1,n2,left_index=True,right_index =True, suffixes = ('Name','Pandas'))
```
## Concate
```
# Series

import pandas as pd
a = pd.Series([1,2,3,4,5,6])
b = pd.Series([11,22,33,44,55,66])
c = pd.concat([a,b])
print(c)
c = pd.concat([a,b], axis = 1)
print(c)
c = pd.concat([a,b], axis = 0)
print(c)
a = pd.DataFrame({'A':[1,2,3,4],'B':[1,2,3,4]})
b = pd.DataFrame({'A':[1,2],'B':[1,2]})
c = pd.concat([a,b], axis = 1,join = 'inner')
print(c)
c = pd.concat([a,b], axis = 1,join = 'outer')
print(c)
c = pd.concat([a,b], axis = 1,join = 'outer',keys=['Py1','Py2'])
print(c)
c = pd.concat([a,b], axis = 0,join = 'inner',keys=['Py1','Py2'])
print(c)
```
## Group By Function
```
import pandas as pd 

s = pd.DataFrame({'name':['a','c','b','e','s','f','r','t','e','d','e','a','a','c','b','e','s','f','r','t','e','d','e','a'],
              'Sub1':[100,49,97,71,27,73,9,43,90,29,82,98,57,13,95,33,39,12,70,16,11,66,29,30],
              'Sub2':[98,42,86,25,77,37,94,19,91,78,55,32,58,8,60,10,82,44,63,95,84,26,98,87]})
s
x= s.groupby('name')
for i,y in x:
    print(i)
    print(y)
    print()
x.get_group('a')
x.get_group('b')
x.min()
x.max()
x.mean()
list(x)
```
## Join
```

import pandas as pd

var1 = pd.DataFrame({'A':[1,2,3,4],'B':[5,6,7,8]})
var2 = pd.DataFrame({'C':[1,2,3,4],'D':[5,6,7,8]})
var1 

var2
var1.join(var2)
```
## Append
```
import pandas as pd

var1 = pd.DataFrame({'A':[1,2,3,4],'B':[5,6,7,8]})
var2 = pd.DataFrame({'C':[1,2,3,4],'D':[5,6,7,8]})
var1 
combined = var1.append(var2, ignore_index=True)
combined
# append method for DataFrames has been removed in Pandas 2.0. This means the method var1.append(var2) is no longer available, and attempting to use it will result in an AttributeError.
```

