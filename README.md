# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. import os and numpy and sys
2. get input from user and form a zero matrix using numpy
3. solve the sum using sys module
4. print the result

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: M.K. JEEVITH
RegisterNumber: 26018300
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected')
    for j in range(i+1,n) :
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')

```

## Output:
<img width="1483" height="987" alt="Screenshot 2026-10-17 085524" src="https://github.com/user-attachments/assets/1229bafd-f820-4d81-9a11-22c5e380e62a" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

