# middle_tn_schools.csv
Data manipulation
#1. Extract data from the given SalaryGender CSV file and store the data from each
column in a separate NumPy array

Code:

import numpy as np
import pandas as pd
df = pd.read_csv('SalaryGender.csv')
df.head()
#a1=np.array(df['Salary'])
for i,col in df.iteritems():
    print(i,np.array(col))

Output:

Salary [140.    30.    35.1   30.    80.    30.    60.    31.1  125.    51.
   3.    46.   150.     3.   130.    15.   130.    84.   190.    74.
  73.    10.    50.     7.     9.5   15.2   28.6   20.    72.    81.
 100.    90.    90.    35.    30.    25.    52.     9.    63.    72.
  16.    92.   106.     2.5    9.    32.    32.    55.    52.    28.
  20.    14.7   22.3   34.8   84.    19.   160.    65.    55.     4.6
 102.    20.    62.    55.    45.6   40.    24.    35.    48.    20.
  40.7   15.     0.25 152.    39.8   12.    30.   120.     1.7   36.
  96.    38.    90.     9.    25.8   22.    38.8   72.    89.    41.
  89.    25.    52.   115.    66.    18.6  152.     1.8   35.     4.  ]
Gender [1 0 0 1 0 0 1 0 1 1 1 1 1 1 1 0 1 0 1 1 0 0 0 0 0 1 1 0 0 1 0 0 0 1 0 1 0
 0 1 1 1 0 1 1 0 0 0 1 1 0 0 0 1 0 0 1 1 0 0 1 1 1 0 1 1 0 0 1 0 0 0 1 0 1
 0 0 1 1 1 1 1 0 1 1 0 0 0 1 1 0 1 0 1 0 0 1 1 1 0 0]
Age [47 65 56 23 53 27 53 30 44 63 22 59 60 28 65 25 65 47 66 45 46 24 60 63
 27 66 36 30 51 65 45 52 54 30 52 26 49 22 34 60 28 58 77 67 27 48 45 49
 36 65 32 49 67 22 49 43 61 43 52 51 66 29 62 56 61 56 41 24 60 43 57 23
 53 71 20 27 69 58 37 32 33 32 60 71 30 62 54 42 62 51 71 29 55 54 55 26
 56 28 44 24]
PhD [1 1 0 0 1 0 0 0 1 1 0 0 1 0 0 0 0 1 1 1 0 0 0 0 0 1 1 0 1 1 1 1 1 0 0 0 0
 0 1 0 0 1 1 0 0 1 0 1 0 1 0 0 0 0 1 0 1 1 0 0 1 0 0 1 0 0 0 0 0 0 0 0 0 1
 0 0 1 1 0 1 1 1 0 0 0 0 0 1 0 1 1 0 1 0 1 0 1 0 0 0]

#2 Find:
1. The number of men with a PhD
2. The number of women with a PhD

Code:
import numpy as np
import pandas as pd
df = pd.read_csv('SalaryGender.csv')
df.head()
df1 = df.filter(['Gender','PhD'])
mens_phd = df1.query("Gender == 1 and PhD == 1")
womens_phd = df1.query("Gender == 0 and PhD == 1")
print('The no of womens are: ',sum(womens_phd['PhD']))
print('The no of mens are: ',sum(mens_phd['PhD']))

Output:
The no of womens are:  15
The no of mens are:  24

#3 Use SalaryGender CSV file. Store the “Age” and “PhD” columns in one DataFrame
and delete the data of all people who don’t have a PhD

Code:

import numpy as np
import pandas as pd
df = pd.read_csv('SalaryGender.csv')
df.head()
#list1=df['Age']
#list2=df['PhD']
#df1= pd.DataFrame(list1,list2)
df1 = df.filter(["Age", "PhD"])

#df1.head()
new_df = df1.drop(age_phd[df1["PhD"] == 0].index)
new_df.head()

Output:

       Age	PhD
0	47	1
1	65	1
4	53	1
8	44	1
9	63	1


#4 Calculate the total number of people who have a PhD degree from SalaryGender
CSV file.


Code:

import numpy as np
import pandas as pd
df = pd.read_csv('SalaryGender.csv')
list2=df['PhD']
count1=0
for j in list2:
    if(j==1):
        count1+=1
print('No of PhD holders are: ',count1)


Output:
No of PhD holders are:  39

#5 How do you Count The Number Of Times Each Value Appears In An Array Of
Integers?


Code:

arr = [0, 5, 4, 0, 4, 4, 3, 0, 0, 5, 2, 1, 1, 9]

counts = [arr.count(a) for a in set(arr)]

print(counts)

Output:

[4, 2, 1, 1, 3, 2, 1]

#6 Create a numpy array [[0, 1, 2], [ 3, 4, 5], [ 6, 7, 8],[ 9, 10, 11]]) and filter the elements
greater than 5.

Code:

import numpy as np
arr=np.arange(0,12)
arr.reshape(4,3)

cond= arr>5
temp=arr[cond]
print(temp)

Output:

[ 6  7  8  9 10 11]

#7 Create a numpy array having NaN (Not a Number) and print it.


Code:

import numpy as np
arr=np.array([ np.nan, 1., 2., np.nan, 3., 4., 5.])
np.unique(arr[~np.isnan(arr)])

Output:
array([1., 2., 3., 4., 5.])

#8 Create a 10x10 array with random values and find the minimum and maximum
values

Code:
import numpy as np
arr=np.random.randint(100,size=(10,10))
print('The min and max element of array are: ',np.min(arr),np.max(arr))

Output:
The min and max element of array are:  0 97

#9 Create a random vector of size 30 and find the mean value

Code:

import numpy as np
arr = np.random.random(30)
print('Mean of array is: ',np.mean(arr))

Output:
Mean of array is:  0.5081032513028907

#10 Create numpy array having elements 0 to 10 And negate all the elements between
3 and 9

Code:

import numpy as np
arr=np.arange(0,10)
print('The original array is: ',arr)
arr[3:9] = np.multiply(arr[3:9],-1)
print('Changed array is: ',arr)

Output:
The original array is:  [0 1 2 3 4 5 6 7 8 9]
Changed array is:  [ 0  1  2 -3 -4 -5 -6 -7 -8  9]

#11 Create a random array of 3 rows and 3 columns and sort it according to 1st column,
2nd column or 3rd column.

Code:

import numpy as np
arr=np.random.randint(50,size=(3,3))
print('The original array is:\n ',arr)
arr.sort(axis=0)
print("Sorted array:\n",arr)

Output:
The original array is:
  [[ 1 48 37]
 [19 19 38]
 [23 25  0]]
Sorted array:
 [[ 1 19  0]
 [19 25 37]
 [23 48 38]]

#12 Create a four dimensions array get sum over the last two axis at once.

Code:
import numpy as np
arr=np.random.randint(50,size=(4,4))
print('The original array is:\n ',arr)
print('The sum of last two row is: ',np.sum(arr[2:3,:]))

Output:
The original array is:
  [[29 21 24 48]
 [26 46 40 28]
 [22 32 21 49]
 [48 41  5 36]]
The sum of last two row is:  124

#13 Create a random array and swap two rows of an array.

Code:

import numpy as np
arr=np.random.randint(50,size=(4,4))
print('The original array is:\n ',arr)
arr[[2,3]]=arr[[3,2]]
print('After swapping: ',arr)

Output:

The original array is:
  [[22 31 47 10]
 [49 38 46  9]
 [ 9  4  6 29]
 [44 14 41 24]]
After swapping:  [[22 31 47 10]
 [49 38 46  9]
 [44 14 41 24]
 [ 9  4  6 29]]

#14 Create a random matrix and Compute a matrix rank.

Code:

import numpy as np
#from numpy import matrix
arr = np.random.rand(3,3)
a=matrix(arr)
r=np.linalg.matrix_rank(a)
print('The rank of matrix is: ',r)

Output:
The rank of matrix is:  3

#15 .Analyse various school outcomes in Tennessee using pandas. Suppose you are a
public school administrator. Some schools in your state of Tennessee are
performing below average academically. Your superintendent, under pressure
from frustrated parents and voters, approached you with the task of understanding
why these schools are under-performing. To improve school performance, you
need to learn more about these schools and their students, just as a business needs
to understand its own strengths and weaknesses and its customers. Though you is
eager to build an impressive explanatory model, you know the importance of
conducting preliminary research to prevent possible pitfalls or blind spots. Thus,
you engages in a thorough exploratory analysis, which includes: a lit review, data
collection, descriptive and inferential statistics, and data visualization.

Code:

import pandas as pd
import matplotlib.pyplot as plt
from scipy.stats import norm
import seaborn as sns
df=pd.read_csv('middle_tn_schools.csv')
df.head()
df.shape
df.describe
df1=df.groupby('school_rating')
df1.head()
df1.describe
c1 = df['reduced_lunch']
c2 = df['school_rating']
correlation = c1.corr(c2)
print(correlation)
corrmat = df1.corr()
#print(corrmat)
f, ax = plt.subplots(figsize=(9, 8))
sns.heatmap(corrmat, ax=ax, cmap="YlGnBu", linewidths=0.1)

plt.scatter(df["school_rating"], df["reduced_lunch"])
plt.grid()
plt.xlabel("Rating")
plt.ylabel("Reduced lunch")
plt.title("School rating vs Reduced lunch")
plt.show()
