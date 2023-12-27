# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

   ![eq1](https://github.com/RAVENPRAVIN/QRdecomposition/assets/146820534/11b8ad9c-c71a-49b2-9a55-31f598c0a773)
  	
   ![eq2](https://github.com/RAVENPRAVIN/QRdecomposition/assets/146820534/e2adc6cf-f978-4d1d-af8f-7cd910da2a08)
   
  ![eq3](https://github.com/RAVENPRAVIN/QRdecomposition/assets/146820534/e5cfa799-aa3e-4efd-9831-6cc82815a8d2)  

  
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
