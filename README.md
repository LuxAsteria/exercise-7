# exercise-7
***
###Abstract
Here in this assignment, I will calculate the trajactories of the dirven nonlinear pendulum,which should be in chaos if some prerequists are satisfied. The method to show the 'chaos situation' is printing the Poincaré section as well as the Lyapnove exponent map.After that, I'm also intersted in the motion of a two-pendulum system, for which I do the **animation simulation**.
***
###Background
>Exercise 3.13 &3.14:
>3.13:Writing a program to calculate and compare the behavior of 2 `nearly identical` pendulums. Use it to calculate the divergence of 2 nearby trajectories in the chaotic regim, as in Figure 3.7,and make a qualitative estimate of the corresponding Lyapunov exponent from the slope of a plot of log(<img src="http://latex.codecogs.com/gif.latex?\Delta\theta" alt="" title="" />) as a function of t.
>3.14:Repeat the previous problem,but give the 2 pendulums slightly different damping factors. How does the value of the Lyapunov exponent compare with that found in Figure 3.7?
***
###Exercise
####Introduction
Oscillatory motion could be found in many areas of physics, here we are going to talk about the motion of pendulums. Lets begin with the simplest one--simple harmonic motion.
This kind of motion involves only one damping factor:the gravity. What's more, the initial angle of such pendulum is rather small so we could take the approximation which suggests<img src="http://latex.codecogs.com/gif.latex?sin(\theta)=\theta" alt="" title="" />.
Thus, it's simple to get the expression:
<img src="http://latex.codecogs.com/gif.latex?\frac{d^{2}\theta}{dt^{2}}=-\frac{g}{l}\theta" alt="" title="" />
Introducing the parameter<img src="http://latex.codecogs.com/gif.latex?\omega" alt="" title="" />,which is associated with <img src="http://latex.codecogs.com/gif.latex?\theta" alt="" title="" />by the equation:
<img src="http://latex.codecogs.com/gif.latex?\frac{d\theta}{dt}=\omega" alt="" title="" />
Hence, the ordinary derivate equation could be rewritten as 2 formulas:
<img src="http://latex.codecogs.com/gif.latex?\frac{d\omega}{dt}=-\frac{g}{l}\theta" alt="" title="" />
<img src="http://latex.codecogs.com/gif.latex?\frac{d\theta}{dt}=\omega" alt="" title="" />
To those equations, we could apply the Euler-Cromer method.
Then, think about other factors, the energy cumsumption, which is prevealing in nature. Here, to simplify the question, we discuss about the factors as a whole, which means use one parameter **q** to discribe it.The equation will change into the following one:
<img src="http://latex.codecogs.com/gif.latex?\frac{d\omega}{dt}=-\frac{g}{l}\theta-q\frac{d\theta}{dt}" alt="" title="" />
Continue to add factors, like the drive force, and discard the approximation, for we want the calculation be more accurate, and finally we'll get the ultimate complete equation:
<img src="http://latex.codecogs.com/gif.latex?\frac{d\omega}{dt}=-frac{g}{l}sin(\theta)-q\omega+F_{D}sin(\Omega_{D}t)" alt="" title="" />

####The next step is to construct the code.
Here's something needed to be highlighted:to ensure the equation is convergent, we have:
<img src="http://latex.codecogs.com/gif.latex?\omega_{i+1}=\omega_{i}-(\frac{g}{l}sin(\theta_{i})+q\omega_{i}-F_{D}sin(\Omega_{D}t))\Delta(t)" alt="" title="" />
<img src="http://latex.codecogs.com/gif.latex?\theta_{i+1}=\theta_{i}+\omega_{i+1}\Delta(t)" alt="" title="" />
<img src="http://latex.codecogs.com/gif.latex?\t_{i+1}=t_{i}+\Delta(t)" alt="" title="" />

####step 1:Visualize the motion of pendulums:

F<sub>D</sub>=0

![image](https://github.com/LuxAsteria/test3/blob/master/gl.gif)

F<sub>D</sub>=0.5

![imagae](https://github.com/LuxAsteria/test3/blob/master/0.5.gif)

F<sub>D</sub>=1.2

![image](https://github.com/LuxAsteria/test3/blob/master/1.2.gif)

[For code please click here](https://github.com/LuxAsteria/exercise-7/new/master)

####step 2:Problem 3.13
Here are Poincaré picture(first) and Lyapnove exponent(second):

####F<sub>D</sub>=0

![image](https://github.com/LuxAsteria/test3/blob/master/ponto%20fd%3D0.png)
![image](https://github.com/LuxAsteria/test3/blob/master/lyap%200%20fd.png)

####F<sub>D</sub>=0.5

![image](https://github.com/LuxAsteria/test3/blob/master/fd%3D0.5%20theta_omega.png)
![image](https://github.com/LuxAsteria/test3/blob/master/lyap%200.5fd.png)

####F<sub>D</sub>=1.2

![e](https://github.com/LuxAsteria/test3/blob/master/omega%3D1:3.png)
![e](https://github.com/LuxAsteria/test3/blob/master/lyap%20ori.png)

*  with different time duration:

![image](https://github.com/LuxAsteria/test3/blob/master/%20fd%3D1.2%20theta_omega.png)
![image](https://github.com/LuxAsteria/test3/blob/master/dr%3D600.png)
![image](https://github.com/LuxAsteria/test3/blob/master/dur%3D900.png)


####step 3:Problem 3.14:

<img src="http://latex.codecogs.com/gif.latex?\Omega_{D}=\frac{2}{3}" alt="" title="" />

![image](https://github.com/LuxAsteria/test3/blob/master/omega%3D1:3.png)
![image](https://github.com/LuxAsteria/test3/blob/master/ponto%20l%3D19.8.png)
![image](https://github.com/LuxAsteria/test3/blob/master/ponto%20l%3D19.8.png)

<img src="http://latex.codecogs.com/gif.latex?\Omega_{D}=\frac{1}{3}" alt="" title="" />

* time=900

![image](https://github.com/LuxAsteria/test3/blob/master/300%201:3%3Dome.png)

* time=300

![image](https://github.com/LuxAsteria/test3/blob/master/300%201:3%3Dome.png)

* lyapnov exponent:

![i](https://github.com/LuxAsteria/test3/blob/master/lyap%201:3%3Dome.png)

* l=19.8
![image](https://github.com/LuxAsteria/test3/blob/master/l%3D19.8%20p%20900.png)
 
* And here's the Lyapnov exponent:

![ia](https://github.com/LuxAsteria/test3/blob/master/l%3D19.8.png)

[For codes please click here](https://github.com/LuxAsteria/exercise-7/new/master)

####step 4:Some Brainstorm:
In addition to the sigle pendulum system, I'm also interested in the double-pendulum system, in which using the Euler-Cromer method would be poor and incompactible.

![image](https://github.com/LuxAsteria/test3/blob/master/double.gif)

[For code please click here](https://github.com/LuxAsteria/exercise-7/new/master)
****
###Conclusion
In this assignment,I investigated how can the differences of damping factors influence the trajectories,Lyapnov exponent,shape of Poincaré picture,etc.
I also successfully actualized the visualization of simulation, by using vpthon as well as matplotlib.
What's more, I furthered my work by simulating the movement of doublependulum.
***
###Acknowledge
[1]Nicolas J. Giordano,Hisao Nkanishi,Computational Physics, second edition.

[2]Jake Vanderplas(vanderplas@astro.washington.edu)

[3]Matplotlib tutorial

##PS:ALL RIGHTS RESERVED
