# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
- Make zeros below the diagonal (upper triangular form).
- Solve the last equation.
- Substitute upward to solve the rest.
- Done — you have all the variables.
```

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: THARANI RAMESHBABU
RegisterNumber: 25018409
*/
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0:
        sys.exit('Divide by zero detected!')
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
    print('X%d = %0.2f'%(i,x[i]), end =' ')
```

## Output:

<img width="1920" height="1080" alt="Screenshot (186)" src="https://github.com/user-attachments/assets/5709c64b-c873-42af-afa9-45b6788cabfa" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

