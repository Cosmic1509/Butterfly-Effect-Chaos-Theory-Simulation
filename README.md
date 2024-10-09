# Butterfly-Effect-Chaos-Theory-Simulation

Bringing Physics to life with simulations has always been a fascianting filed of study for me. As ever since my 12th grade I started to be more amazed by the different theories and applications of physics concepts which include mathematical equations for detailed explanation. 
The Butterfly Effect is a concept that I have read a long time ago. Since, I know the mathematical equations and procedure, I thought well lets try to simulate it. 
The Butterfly Effect (The chaos effect) is the sensitive dependence on initial conditions in which small change in one state of a [deterministic non-linear system](https://en.wikipedia.org/wiki/Nonlinear_system). which results in large differences in a later state. The project were doing is to simulate the earths atmospheric convection. The atmospheric convection is nothing bu the basic theory of hot air going up to the earhts atmosphere and the cool air decending downward, which in turn produces the butterfly effect. 
It basically breaks down to that small occurances may have large effects in weather. Basically there was a research paper that talked about how the flap of a butterfly in Africa can produce cyclonic occurances somewhere in north america. 

Initially Lorentz had decuded 12 parameters to determine the butterly effect, but turns out he had seen very abrnormal outputs that made the system extremely chaotic, so he finally came with the conclusion of 3 parameters which were deduced by Edward Norton Lorentz himself, and they were differential equations:

$\frac{dx}{dt} = \sigma(y - x) $

$\frac{dy}{dt} = x(\rho - z) - y $

$\frac{dz}{dt} = xy - \beta z $

The equations depict the dynamics of a uniformly warmed fluid layer with cooling from above in a two-dimensional setting.
They specifically capture the temporal evolution of three quantities:

* $x$ represents the **rate of convection**, 
* $y$ corresponds to the **horizontal temperature variation**,
* $z$ accounts for the **vertical temperature variation**.

In this project I have used Python 3.5 and have used various libraries such as:
numpy, matploblib.pyplot, matplotlib.animation, FuncANimation, scipy.integrate and odeint. 

With the help of these libraries I have achieved the plot of the butterfly effect, perfect animation using time intervals between 0-40 seconds and odeint inorder to solve the differential equations using 2 different inputs (model, initial position and time points).

**Constants of Lorentz Attractor and Variables:**
A plot of Lorenz' [strange attractor](https://en.wikipedia.org/wiki/Attractor#Strange_attractor) for values ρ=28, σ = 10, β = 8/3. The butterfly effect or sensitive dependence on initial conditions is the property of a dynamical system that, starting from any of various arbitrarily close alternative initial conditions on the attractor, the iterated points will become arbitrarily spread out from each other.
The constants are defined as follows:
* **Prandtl number $\sigma$**: Rate of heat transfer in the system.
* **Rayleigh number $\rho$**: Onset of convection and the overall behavior of the system.
* **Physical Dimension $\beta$**: Ratio of the width-to-height aspect ratio of the convecting cell in the system.

Lorenz used the values which is where the system begun to behave chaotically:
* $\sigma = 10$
* $\rho = 28$
* $\beta = 8/3$
  
```Odient``` the very important function to be used with this theory. The function  ```odeint``` is used to simulate the evolution of a dynamic system described by three ordinary differential equations:
Inputs:
* Initial Condition of the system (```position_0```)
* A function describing the system of ode's $\frac{d\vec{S}}{dt} = A * \vec{S}$ (```system_of_odes```) desrcibes out vector of x, y and z.
* The temproal domain in which we want to solve the system (```time_points```) 
* Additional Arguments (```sigma, beta, rho```)

We now know about the function odeint and what inputs are required to obtain the solution in the temporal domain. But now we need to figure out how to solve the differntial equation using eulers method :
* We have $S_0$ at $t = t_0$ (Initial Condition) -> We want $S_1$ at $t = t_1$
* We get $S_1$ utilizing the numerical scheme for calculating derivatives:

The discrete derivatives in eulers method
$$\frac{S_1 - S_0}{\Delta t} 
Continuous Derivative: 
\frac{dS}{dt}$$ 

Equating both of the derivative we can obtain the value of $S_1$: <br>
</br>
$$\frac{S_1 - S_0}{\Delta t} = \frac{dS}{dt}$$
<br>
$$S_1 = S_0 + \Delta t \frac{dS}{dt}$$ </br>

We have $\Delta t$ (interval of ```time_points```) we need $\frac{dS}{dt}$.
* We get $\frac{dS}{dt}$ by replacing $S_0$ in our system of odes:

$\frac{dx}{dt} = \sigma(y_0 - x_0) $

$\frac{dy}{dt} = x_0(\rho - z_0) - y_0 $

$\frac{dz}{dt} = x_0 y_0 - \beta z_0 $

* Once we computed $S_1$, we repeat the process across all time points.


Inorder to Plot the result that we obtained and simulate it we must use the following code:

```
fig, ax = plt.subplots(subplot_kw={'projection':'3d'})

ax.plot(x_sol, y_sol, z_sol)
plt.show()
```
![image](https://github.com/user-attachments/assets/fae7e6be-649f-4637-b9c9-645d6423d007)



![image](https://github.com/user-attachments/assets/3c18c624-dc62-4884-8a56-90b005daf5e1)

