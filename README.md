# How-to-Talk-Linear-Regression

november 18, 2018

I appreciate comments. Shoot me an email at noel_s_cruz@yahoo.com!

Hire me!

Linear Regression is fitting a line to a bunch of points. We take the average
squared error MSE to that line and is actually the variance of the distribution.

So we parameterize that line as y = ax + b where a is slope and b is the 
intercept. This is true for single predictor variable x or in one dimension.

The line fitting problem

Pick a line (parameters a, b) suited to the data, (x(1), y(1)),...(x(n), y(n))
element of RxR

-x(i), y(i) are predictor and response variables, e.g. SAT score, GPA of ith student.
- Minimize the mean squared error,

    MSE(a,b) = 1/n times summation from i=1 to i=n (y(i) - (ax(i) + b))2

This is the loss function.

    L(a,b) = summation from i=1 to i=n (y(i) - (ax(i) + b))2

We minimize by taking derivatives and set dL/da = dL/db = 0

We want to find the line that incurs the least MSE. The line is defined by 
parameters a & b.

b = ybar minus atimesxbar, ybar equals ymean
a = Covariance of x & y divided by Variance of x

LR is cornerstone of statistics.

##############
Regression with multiple predictor variables

Least-squares Regression

Least-squares solution 1

Linear function of d variables given by w element of Rd and b element of R:

  f(x) = w1x1 + w2x2 + ... + wdxd + b = w.x + b
  
  L(w,b) = summation from i=1 to i=n (y(i) - (w.x(i) + b))2
  
Assimilate the intercept b into w:
-Add a new feature that is identically 1: let xtwiddle = (1,x) element of Rd+1

  (4 0 2 ... 3)   ==>> (1 4 0 2 ... 3)

-Set wtwiddle = (b,w) element of Rd+1
-Then f(x) = w.x + b = wtwiddle times xtwiddle = (b,w).(1.x) = b + w.x

Goal: find wtwiddle element of Rd+1 that minimizes

    L(wtwiddle) = summation from i=1 to i=n (y(i) - (wtwiddle.xtwiddle(i)))2
    
Rewriting as purely matrix vector product, the loss function is:

    L(wtwiddle) = summation from i=1 to i=n (y(i) - (wtwiddle.xtwiddle(i)))2 = ||y - Xwtwiddle||2
    
    L(wtwiddle) = ||y - Xwtwiddle||2
    
with no summation and it minimized at wtwiddle = (XofTX)raisedto-1(XofTy).

##############
Regularized Regression

Ridge Regression

    L(w,b) = summation from i=1 to i=n (y(i) - (w.x(i) + b))2 + lambda||w||2
      
      where lambda||w||2 is a penalty term called "regularizer"
    w = (XofTX + lambdaI)raised to-1(XofTy)

Popular "shrinkage" estimators

Ridge Regression

    L(w,b) = summation from i=1 to i=n (y(i) - (w.x(i) + b))2 + lambda||w||22   L2 norm

Lasso, tends to produce sparse w

    L(w,b) = summation from i=1 to i=n (y(i) - (w.x(i) + b))2 + lambda||w||1    L1 norm
 
##############
Linear Models for conditional probability estimation

Squashing Function

    s(z) = 1/(1 + eto-z)  element of [0,1]
    
    s(+infinity) = asymptotic to 1
    s(0) = 1/2
    s(-infinity) = asymptotic to 0
 
##############
Logistic Regression
    
Model parametrized by w element of Rd and b element of R:

    Prw,b(y|x) = 1/(1 + eto-y(w.x+b))
    
Learn parameters w,b from data

Gradient descent procedure for logistic regression

Given (x(1),y(1)),...,(x(n),y(n)) element of Rd c{-1,1}, find

    arg minL(w) = summation from i=1 to i=n ln(1 + eto-y(i)(w.x(i)))

-Set w0 = 0
-For t = 0,1,2,..., until convergence:

    wt+1 = wt + etat times summation from i=1 to i=n y(i)x(i) Prwt(-y(i)|x(i)) 
  
  where etat is a "step size"

##############  
A logistic regression approach

Code positive as +1 and negative as -1.

    Prw,b(y|x) = 1/(1 + eto-y(w.x+b))
    
Given training data (x(1),y(1)),...,(x(n),y(n)) element of Rd x {-1,1}, find w,b
minimizing

    L(w,b) = summation from i=1 to i=n ln(1 + eto-y(w.x(i)+b))
    
Convex problem with many solution methods, e.g.

-gradient descent, stochastic gradient descent
-Newton-Raphson, quasi-Newton

All converge to the optimal solution.

I included some posts for reference.

https://github.com/noey2020/How-to-Talk-Statistics-Pattern-Recognition-101

https://github.com/noey2020/How-to-Write-SPI-STM32

https://github.com/noey2020/How-to-Write-SysTick-Handler-for-STM32

https://github.com/noey2020/How-to-Write-Subroutines-in-C-Assembly-STM32

https://github.com/noey2020/How-to-Write-Multitasking-STM32

https://github.com/noey2020/How-to-Generate-Triangular-Wave-STM32-DAC

https://github.com/noey2020/How-to-Generate-Sine-Table-LUT

https://github.com/noey2020/How-to-Illustrate-Multiple-Exceptions-

https://github.com/noey2020/How-to-Blink-LED-using-Standard-Peripheral-Library

I appreciate comments. Shoot me an email at noel_s_cruz@yahoo.com!

Hire me!

Have fun and happy coding!
