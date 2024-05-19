# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
Program to implement the linear regression using gradient descent.
Developed by: 
RegisterNumber:  
*/
```
import numpy as np
import matplotlib.pyplot as plt
data=pd.read_csv("ex1.txt",header=None)
plt.scatter(data[0],data[1])
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City(10,000s)")
plt.ylabel("Profit ($10,000)")
plt.title("Profit Prediction")
def computeCost(X,y,theta):
    m=len(y) 
    h=X.dot(theta) 
    square_err=(h-y)**2
    return 1/(2*m)*np.sum(square_err) 
data_n=data.values
m=data_n[:,0].size
X=np.append(np.ones((m,1)),data_n[:,0].reshape(m,1),axis=1)
y=data_n[:,1].reshape(m,1)
theta=np.zeros((2,1))
computeCost(X,y,theta) 
def gradientDescent(X,y,theta,alpha,num_iters):
    m=len(y)
    J_history=[] #empty list
    for i in range(num_iters):
        predictions=X.dot(theta)
        error=np.dot(X.transpose(),(predictions-y))
        descent=alpha*(1/m)*error
        theta-=descent
        J_history.append(computeCost(X,y,theta))
    return theta,J_history
theta,J_history = gradientDescent(X,y,theta,0.01,1500)
print("h(x) ="+str(round(theta[0,0],2))+" + "+str(round(theta[1,0],2))+"x1")
plt.plot(J_history)
plt.xlabel("Iteration")
plt.ylabel("$J(\Theta)$")
plt.title("Cost function using Gradient Descent")
plt.scatter(data[0],data[1])
x_value=[x for x in range(25)]
y_value=[y*theta[1]+theta[0] for y in x_value]
plt.plot(x_value,y_value,color="r")
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City(10,000s)")
plt.ylabel("Profit ($10,000)")
plt.title("Profit Prediction")
def predict(x,theta):
    predictions=np.dot(theta.transpose(),x)
    return predictions[0]
predict1=predict(np.array([1,3.5]),theta)*10000
print("For Population = 35000, we predict a profit of $"+str(round(predict1,0)))
predict2=predict(np.array([1,7]),theta)*10000
print("For Population = 70000, we predict a profit of $"+str(round(predict2,0)))

```

## Output:
!(![Screenshot 2024-05-19 112907](https://github.com/premsuryas/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/147473858/e0acada0-3958-487c-b953-64f45a82a781)
)
!(![Screenshot 2024-05-19 112920](https://github.com/premsuryas/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/147473858/39961d3d-62c4-44fe-8ad3-3641abdaae9f)
)
!(![Screenshot 2024-05-19 114931](https://github.com/premsuryas/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/147473858/19d27378-c1ca-4002-af36-d7843819099a)
)
!(![Screenshot 2024-05-19 114941](https://github.com/premsuryas/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/147473858/0381376f-868d-4edf-8caa-cf9fab3386dc)
)
!(![Screenshot 2024-05-19 114948](https://github.com/premsuryas/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/147473858/cf6535d4-283e-43e7-8f34-5bf6703b73ef)
)


# Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
