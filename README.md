# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step1 : 
the number of unknowns n, then read the augmented matrix a[n][n+1] and initialize solution array x[n] using NumPy.

### Step 2:
Check for zero pivots in the diagonal a[i][i], if found, exit using sys.exit() to prevent division by zero.

### Step 3: 
For each row below pivot, calculate the ratio = a[j][i] / a[i][i] and eliminate lower entries using a[j][k] -= ratio * a[i][k].

### Step 4:
Initialize last variable: Compute x[n-1] = a[n-1][n] / a[n-1][n-1].

### Step 5:
Back Substitution: For rows i = n-2 to 0, compute x[i] by subtracting known terms and dividing by pivot: x[i] = (a[i][n] - Σ a[i][j]*x[j]) / a[i][i].

### Step 6:
Output the solution vector x using a loop and formatted print() statements.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Eesha Ranka
RegisterNumber: 212224240040 
*/

import numpy as np
import sys

n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)

for i in range(n):
    for j in range (n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by Zero detected')
    
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
    
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
![image](https://github.com/user-attachments/assets/a83bbb9f-b775-44f7-91d2-0fdc7d683704)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

