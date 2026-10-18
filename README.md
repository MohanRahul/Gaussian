# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start the program and read the order of the matrix.
2. Read the elements of the augmented matrix.
3. Check the pivot element and detect division by zero.
4. Perform forward elimination to convert the matrix into upper triangular form
5. Apply back substitution to calculate the values of the unknown variables.
6. Display the solutions of all variables and stop the program.
7. print the final result 

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Mohan Rahul s
RegisterNumber: 26018134
*/
```
import os 

os.environ["OPENBLAS_NUM_THREADS"] = "1"

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
        sys.exit('divide by zero detected!')
    for j in range(i+1,n):
        ratio= a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k]-ratio*a[i][k]
            
x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %.2f'%(i,x[i]),end=' ')
        
    


## Output:
![gaussian elimination]()
<img width="1032" height="638" alt="image" src="https://github.com/user-attachments/assets/b2d8c664-e565-416f-ae40-c6e8a327c919" />

<img width="1233" height="622" alt="image" src="https://github.com/user-attachments/assets/e92fbf05-5510-4e48-87d1-1e8a189928ed" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

