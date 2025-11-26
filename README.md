# SIMULATION-OF-MEAN-AND-VARIANCE-USING-SCILAB-
__AIM:__

To write a program for mean, variance and cross correlation in SCILAB and verify the output. 

__EQUIPMENTS NEEDED:__

.Computer with i3 Processor 

.SCI LAB 

__ALGORITHM:__

1. Define the Function: Specify the function you want to simulate. For example, 
f(x)=sin⁡(x)f(x)=sin(x) or any other function. 
2. Generate Sample Points: Decide on the range and the number of sample points. Generate 
these sample points within the desired range. 
3. Evaluate the Function: Compute the function values at each of these sample points. 
4. Compute Mean, Variance and Cross Correlation: Use Scilab's functions to calculate the 
mean and variance of the computed function values. 
5. Display Results: Output the computed mean variance and Cross Correlation 

__PROCEDURE:__ 

1.Refer Algorithms and write code for the experiment. 

2.Open SCILAB in System 

3.Type your code in New Editor 

4.Save the file 

5.Execute the code If any Error, correct it in code and execute again 
  
6.Verify the generated results

__PROGRAM:__
```
clear;
clc;

// ---------- Mean Value ----------
function X = f(x)
    z = 3*(1 - x)^2; // Marginal Probability Density Function 
    X = x * z;
endfunction

a = 0;
b = 1;
EX = intg(a, b, f); // Mean value of X 

function Y = c(y)
    z = 3*(1 - y)^2; // Marginal Probability Density Function 
    Y = y * z;
endfunction

EY = intg(a, b, c); // Mean value of Y 

disp("i) Mean of X = " + string(EX));
disp("Mean of Y = " + string(EY));

// ---------- Variance ----------
function X = g(x)
    z = 3*(1 - x)^2; // Marginal Probability Density Function 
    X = x^2 * z;
endfunction

EX2 = intg(a, b, g);

function Y = h(y)
    z = 3*(1 - y)^2; // Marginal Probability Density Function 
    Y = y^2 * z;
endfunction

EY2 = intg(a, b, h);

vX2 = EX2 - (EX)^2; // Variance of X 
vY2 = EY2 - (EY)^2; // Variance of Y 

disp("ii) Variance of X = " + string(vX2));
disp("Variance of Y = " + string(vY2));

// ---------- Cross Correlation ----------
x = input("Type in the reference sequence = ");
y = input("Type in the second sequence = ");

// Use xcorr instead of corr to avoid "wrong number of output arguments" error
r = xcorr(x, y);

plot2d3('gnn', r);
xtitle("Cross-Correlation between x and y", "Lag", "Correlation Value");
```
__OUTPUT GRAPH:__

<img width="864" height="926" alt="image" src="https://github.com/user-attachments/assets/21bfbaef-d089-4b43-ae9c-3cae90b93f10" />


__RESULT:__

<img width="887" height="369" alt="image" src="https://github.com/user-attachments/assets/7e074576-cbb2-4e9c-8417-7be9698443b9" />

