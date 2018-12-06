#Day 17 Homework 3
#Monte Carlo Method
#Double Integral

import numpy as np
import random

nts=1000 #Number of runs

xi=0.
xf=1.
yi=0.
yf=1.
x=np.linspace(xi,xf,nts)
y=np.linspace(yi,yf,nts)

xi_circle=.5-1./3.
xf_circle=.5+1./3.
x_circle=np.linspace(xi_circle,xf_circle,nts)
circleY=.5+(np.sqrt((1./9.)-((x_circle-.5)**2)))

dx=x[1]-x[0]
dy=y[1]-y[0]

A=np.zeros((nts,nts))
def function(X,Y):
    return np.log(1+X*Y)
    
def midpoint():   
    for i in range(nts):
        for j in range(nts):
            if ((y[j]>circleY[j]) or (y[j]<(1-circleY[j]))):
                A[i,j]=function(x[i]+dx/2,y[j]+dy/2)*dy*dx
    I=sum(A)
    I=sum(I)
    return A,I
    
Iv,In=midpoint()
print "The double integral using midpoint method is",In
    
I=np.zeros((nts,nts))
def MC_func(nts):
    for i in range(nts):
        for j in range(nts):
            rx=random.randint(0,nts-1)
            ry=random.randint(0,nts-1)
            I[i,j]=Iv[rx,ry]
    II=sum(I)
    return sum(II)
II=MC_func(nts)
print "The double integral using MC method is",II
