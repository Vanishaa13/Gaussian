# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start

2. Read the number of unknowns n.

3. Initialize an augmented matrix A of size n × (n+1).

4. Read the elements of the augmented matrix A.

5. For i = 0 to n-1:
   
      a. Check whether A[i][i] is zero.
   
      b. If A[i][i] = 0, display "Divide by zero detected!" and stop.
   
      c. For j = i+1 to n-1:
   
            i. Calculate ratio = A[j][i] / A[i][i].
   
           ii. For k = i to n:
   
                  A[j][k] = A[j][k] - ratio × A[i][k].

7. Perform back substitution:
   
      a. Calculate the last variable:
   
            X[n-1] = A[n-1][n] / A[n-1][n-1].
      b. For i = n-2 down to 0:
   
            i. Set X[i] = A[i][n].
   
           ii. For j = i+1 to n-1:
   
                  X[i] = X[i] - A[i][j] × X[j].
   
          iii. Calculate:
   
                  X[i] = X[i] / A[i][i].

9. Display X0, X1, ..., Xn-1 up to two decimal places.

10. Stop.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: 
RegisterNumber: 
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
        sys.exit("Divide by zero detected!")
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(i,n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f "%(i,x[i]), end = "")
*/
```

## Output:


![alt text](<Screenshot 2026-08-18 095117.png>)



![alt text](<Screenshot 2026-08-18 095125.png>)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

