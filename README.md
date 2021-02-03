# Linear Regression using Gradient Descent  

## Linear Regression   
In statistics, linear regression is a linear approach to modelling the relationship between a dependent variable and one or more independent variables. 
Let **X** be the independent variable and **Y** be the dependent variable.   
  Y = mX + c  
  
Equation is used to train our model with a given dataset and predict the value of **Y** for any given value of **X**.   
Challenege is to determine the value of **m** and **c**, such that the line corresponding to those values is the best fitting line or gives the minimum error.  

## Loss function  
The loss is the error in our predicted of **m** and **c**. Goal is to minimize this error to obtain the most accurance value of **m** and **c**.  
Mean Squared Error function is used to calculate the loss. 
There are three steps in this function:
1. Find the difference between the actual y and predicted y value(y = mx + c), for a given x.  
2. Square this difference.
3. Find the mean of the squares for every value in X.  
  E = \frac{1}{n} \sum_{i=0}^n (y_i - y_i')^2  

Here y_i is the actual value and y_i' is the predicted value. Lets substitue the value of y_i'
  E = \frac{1}{n} \sum_{i=0}^n (y_i - (mx_i + c))^2

## The Gradient Descent Algorithm  
Gradient descent is an iterative optimization algorithm to find the minimum of a function.  
 
1. Initially let m = 0 and c = 0. Let L be our learning rate. This controls how much the value of **m** changes with each step. L could be a small value like 0.0001 for good accuracy. 
2. Calculate the partial derivative of the loss function with respect to m, and plug in the current values of x, y, m and c in it to obtain the derivative value **D**.  
    D_m = frac{1}{n} \sum_{i=0}^n 2(y_i - (mx_i + c))(-x_i)
    D_m = frac{-2}{n} \sum_{i=0}^n x_i(y_i - y_i')   
D_m is the value of the partial derivative with respect to **m**. Similarly lets find the partial derivative with respect to **c**, D_c :   
    D_c = frac{-2}{n} \sum_{i=0}^n (y_i - y_i')
3. Now update the current value of **m** and **c** using the following equation: 
    m = m - L x D_m  
    c = c - L x D_c  
4. Repeat this process untill our loss function is a very small value or ideally 0 (which means 0 error or 100% accuracy). The value of **m** and **c** that we are left with now will be the optimum values.  
  
