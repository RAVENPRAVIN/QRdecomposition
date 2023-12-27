# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

  ![ex4](https://github.com/RAVENPRAVIN/QRdecomposition/assets/146820534/161e7bef-65e3-4ffa-ab21-9213f9b2b8cb)

  ![ex6](https://github.com/RAVENPRAVIN/QRdecomposition/assets/146820534/07ce2c27-cde9-4708-9bb7-b4dd2ef1060c)

  ![ex3](https://github.com/RAVENPRAVIN/QRdecomposition/assets/146820534/3ff2b3cb-98ed-4985-8076-64bdf0b42f51)

  
3.	Obtain the Q matrix
   
    ![ex1](https://github.com/RAVENPRAVIN/QRdecomposition/assets/146820534/de78309b-c739-4b45-a043-6b4b3b47bea5)
  	
5.	Construct the upper triangular matrix R

  ![ex2](https://github.com/RAVENPRAVIN/QRdecomposition/assets/146820534/0eebfb75-3b56-41bc-bc73-94958954f34a)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: PRAVIN KUMAR A
RegisterNumber: 212223230155
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.zeros((n,n))
    u=np.zeros((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
a=np.array(eval(input()))
QR_Decomposition(a)
```

## Output
![EX08](https://github.com/RAVENPRAVIN/QRdecomposition/assets/146820534/c7c2b366-9c35-4ec0-8032-69d788b83ae2)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
