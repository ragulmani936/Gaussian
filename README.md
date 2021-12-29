# Gaussian Elimination with partial pivoting

## AIM:
To write a program to find the Gaussian Elimination with partial pivoting of a matrix.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step 1:
Import the numpy module to use the built-in functions for calculation.

### Step 2:
Import the sys module to use the built-in functions.

### Step 3:
Get input from the user for number of rows and add it by 1 for number of columns.

### Step 4:
Using np.zeros() set the matrix as null matrix.

### Step 5:
Using nested for loop get input from the user for each element in the matrix.

### Step 6:
Using nested for loop find the ratio and perform the elementary row operations and find the final matrix.

### Step 7:
Use back substitution method to find the value of the variables and print it.

### Step 8:
End the program.

## Program:
```
Program to find the Gaussian Elimination with partial pivoting of a matrix.
Developed by:Ragul M 
RegisterNumber:21500303  
```
~~~
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
X = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected')
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
X[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    X[i] = a[i][n]
    for j in range(i+1,n):
        X[i] = X[i] - a[i][j]*X[j]
    X[i] = X[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,X[i]), end = ' ')
 ~~~


## Output:
![gaussian elimination](https://github.com/ragulmani936/Gaussian/blob/main/Screenshot%20(36).png?raw=true)


## Result:
Thus the program to find the Gaussian Elimination with partial pivoting of a matrix is written and verified using python programming.

