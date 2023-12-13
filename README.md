# Simulation of Schrödinger Equation with PINN  

In this application, it was aimed to speed up the processing time by creating an artificial neural network that approximates the numerical solutions of the Schrödinger equation, one of the important equations of quantum mechanics. For this purpose, the TensorFlow library of the Python language was used to create artificial neural networks. TensorFlow is an open source Python library used for machine learning and deep learning applications. TensorFlow is based on a graph-based computational model. This allows the program to optimize its calculations by thinking of them as a graph. In addition, the TensorFlow library can be used in Python, C++, Java, Go and many other languages.The Schrodinger equation in one dimension is as follows:  
$$-\frac{i \hbar}{2m}\frac{\partial^2 \psi(x,t)}{\partial x^2}+V(x)\psi(x,t)=i\hbar\frac{\partial \psi(x,t)}{\partial t}$$

Now, letting $\psi(x,t)=u(x)T(t)$ for seperation of variables, we have:  
$$T(t)(-\frac{i\hbar}{2m}\frac{d^2 u(x)}{dx^2}+V(x)u(x))=i\hbar u(x)\frac{dT(t)}{dt}$$  

then dividing by $u(x)T(t)$:

$$i \hbar \frac{1}{T(t)}\frac{dT(t)}{dt}=-\frac{1}{u(x)}\frac{\hbar^2}{2m}\frac{d^2u(x)}{dx^2}+V(x)=E$$  

which is set to a time and space independent constant since each side is only dependent on  x or t, which are two independent variables.  

$$i\hbar \frac{dT(t)}{dt}=ET(t)  \quad\quad  so, \quad\quad    T(t)=exp(\frac{-iEt}{\hbar})$$  

where u(x) solves the time-independent schrodinger equation:  

$$-\frac{\hbar^2}{2m}\frac{d^2u(x)}{dx^2}+V(x)u(x)=Eu(x)$$  

inally, by normalizing the wave equation ($\psi$), the equation we will use to calculate the probability of the particle being in the box is:  


$$|\psi(x,t)|^2dx  \quad\quad     so,    \quad\quad   \int \psi \psi^{*}  dx$$

The probability that the particle is in a box of width dx centered at x:

$$|\psi(x,t)|^2=|u(x)|^2 exp(\frac{-iEt}{\hbar})exp(\frac{iEt}{\hbar})=|u(x)|^2$$

As can be seen from the equations, time dependence is not taken into account when calculating probability. Basically, what we will do in this application is to solve $u(x)$ and plot its graph. Also note that the probability is proportional to $u(x)^2$. This means that any positive or negative value will have large effects.
