Some differential equations can be recast as integral equations to give a deeper understanding of different techniques. Typically this is done by using the corresponding Green's function for the differential equation. As a result of using the Green's function the boundary conditions are encoded into the integral form of the differential equation. We can also see this transformation in the integral form of Maxwell's equations.

## Classification of Integral equations
---
For the purposes of this class we will classify integral equations along three different axes. We will also largely be talking about ODE integral equations in this discussion instead of PDE solutions **and potentially only second order ODEs as well**. So keep that in mind.

1. Limits
	1. Constant/Fixed limits $\Rightarrow$ Fredholm equation
	2. One limit is x dependent $\Rightarrow$ Volterra equation
2. Where the unknown is
	3. Only in the integral $\Rightarrow$ Type 1
	4. Not only in the integral $\Rightarrow$ Type 2
3. Homogeneous vs. Inhomogeneous
	1. Is there are source term or not?

Each of these classifications suggests a different kind of approach to solve them which is what the rest of this chapter will largely be about. Specifically a lot of these methods will make analogies to finite dimensional matrices to justify their logic. 

## Integral Transforms
---
The main tool we will use to solve these different equations are integral transforms. Each of these will be useful for a few different situations. Some of these you are already familiar with!

>[!info] Fourier Transforms
>Useful for Fredholm equations with a kernel that has the form $K(x-y)$
>$$\tilde{u}(k) = \mathscr{F}(u) = \int_{-\infty}^{\infty}u(x) e^{ikx} dx$$
>$$u(x) = \mathscr{F}^{-1}(\tilde{u}) = \int_{-\infty}^{\infty} \tilde{u}(k) e^{-ikx} \frac{dk}{2\pi}$$