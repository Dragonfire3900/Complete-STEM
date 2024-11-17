The main two features of real waves which complicate things are dispersion and non-linearity. We will examine both of these as well as some methods which attempt solutions to them.

# Dispersive waves
---
Generally this is a dependence of the speed of propagation on the frequency of the wave. There are many different examples that we are going to work through in order to describe the general process of how to work with these solutions

### Ocean Waves
In general this problem works by imposing that the Laplacian of the velocity potential is zero every where in the bulk ($\nabla^2 \phi =0$) along with the following boundary conditions
$$\begin{gather*}
	\frac{\partial \phi}{\partial y} = 0 \text{, on } y=0 \\
	\frac{\partial \phi}{\partial t} + 
		\frac{1}{2}\left(\nabla \phi\right)^2 + gy =0 \text{, on the free surface } y=h \\
	\frac{\partial h}{\partial t} - \frac{\partial \phi}{\partial y}
		+ \frac{\partial h }{\partial x} \frac{\partial \phi}{\partial x}=0
		\text{, on the free surface } y=h
\end{gather*}$$
The difficulty with the second two boundary conditions is that they are non-linear since they involve the products of derivatives. However, we can work only with small amplitude waves which linearizes these boundary conditions. In particular through small wave approximations, any terms the have the product of multiple derivatives have those terms suppressed

>[!info] Small wave approximations & Linearization
>This process of linearizing differential equations through small wave approximations is entirely general. Through a small wave approximation a differential equation that has the product of two derivatives can have those terms suppressed such as follows
>$$\frac{\partial \phi}{\partial t} + \frac{1}{2}\left(\nabla \phi\right)^2 + gy =0 \Rightarrow \frac{\partial \phi}{\partial t} + gy = 0$$
>Which can make systems like this much easier to solve and work with. 
>
>I think that this does only work if the Taylor series can be defined for this potential since that's kind of what we are working with but I am not 100% certain

Using this we can transform the boundary condition by eliminating the need for the height of the water. This gives another differential equation as a boundary condition that must be satisfied. In particular, we can guess a particular form of the solution to this problem (using the knowledge of Laplacians) which will be transformed under this boundary condition. Using this we can get a relationship between the angular frequency and the wave number of our solution. For this case it's of the form $\omega^2 = g k \tanh(k h_0)$. These are called dispersion equations.

>[!info] Dispersion equations/relationships
>These relationships are something which relates the angular frequency of some solutions to the wave number of the solutions. In a simple linear system this relationship is very straight forward typically being a proportionality. However, in non-linear systems the dispersion relationship can play a big role in how things evolve over time

### Group Velocity
As a result of the dispersion relationship there is a difference between how the individual waves in a packet evolve vs. how the entire packet evolves. This is because each of the Fourier components will end up traveling at a slightly different speed meaning that the packet will tend to spread out over time. 

| Group velocity                                       | Phase Velocity                          |
| ---------------------------------------------------- | --------------------------------------- |
| $\Large U \equiv \frac{\partial \omega}{\partial k}$ | $\Large v_p \equiv \frac{\omega(k)}{k}$ |
