The general idea of working with Calculus of variations is "How do we optimize a functional for the best path". This is kind of similar to finding the optimal path in CS but is continuous and imposes some important restrictions

>[!info] Functional Definition
>In words a functional is some type of function which takes in a function and maps it to some scalar space. Formally this would be written as follows
>$$ J: C^\infty(\mathbb{R}) \rightarrow \mathbb{R} $$
>Where $J$ is the functional and $C^\infty(\mathbb{R})$ indicates the continuous infinitely differentiable functions over the real numbers
 
In this class we will be specifically dealing with functionals that are integrals of the form
$$
J\left[y\right] = \int_{x_1}^{x_2} f(x, y, y', y'', \dots y^{(n)}) dx
$$
Since this functional depends on a finite number of derivatives in $y$ it is considered "local". Think of this property kind of arising from Taylor series. We can vary the function $y$ by making the perturbation $y(x) \rightarrow y(x) + \epsilon \eta(x)$ where $\epsilon$ is some small constant. We can then measure the change in the functional by taking the difference between the original path and this altered path. The overall result for a functional which only depends on $x$, $y$, and $y'$ is as follows
$$
J[y + \epsilon \eta] - J[y] =
	\left[\epsilon \eta \frac{\partial f}{\partial y'}\right]_{x_1}^{x_2} +
	\int_{x_1}^{x_2} (\epsilon \eta(x)) \left\{
		\frac{\partial f}{\partial y} - \frac{d}{dx}\left(
			\frac{\partial f}{\partial y'}
		\right)
	\right\} dx + O(\epsilon^2)
$$
The first term in this can be considered a "surface" term since it requires evaluating the functional at the boundary. For fixed end points this term vanishes but can be considered if there is a constraint on the boundary. This will show up later on. However, this particular form gives rise to the definition of the functional derivative

>[!info] Functional (Frechet) Derivative / Euler-Lagrange Equation
>This is the full form which includes higher order dependence. For lower order dependence it simplifies as shown in the above equation.
>$$ \frac{\partial J}{\partial y} = \frac{\partial f}{\partial y} - \frac{d}{dx}\left(\frac{\partial f}{\partial y'}\right) + \frac{d^2}{dx^2} \left(\frac{\partial f}{\partial y''}\right) - \frac{d^3}{dx^3} \left(\frac{\partial f}{\partial y^{(3)}}\right) + \dots$$
> As you can see there is an overall pattern. In additional the first order form of this equation is typically called the **Euler-Lagrange equation**

When we are seeking to optimize a functional we are looking to solve this differential equation for when $\frac{\partial J}{\partial y} = 0$ as this will give the stationary points for this functional. It's this fundamental problem that we are looking so solve. Typically this is done by finding the Lagrangian since the action can be put in terms of the functional typically called the "action" $S$. 

There are many different types of tricks to solve these functional problems many of which are not written here (>.>) but they can be reviewed independently. One of importance is a simplification trick which can reduce the difficulty of the functional problem. If the functional $f$ has no explicit dependence on $x$ then it's total derivative can be simplified which simplifies the Euler Lagrange equation. Specifically this gives rise to the **first integral** of the Euler equation.
$$
\frac{d}{dx}\left(f - y' \frac{\partial f}{\partial y'}\right) = y' \left(
	\frac{\partial f}{\partial y} - \frac{d}{dx}\left(\frac{\partial f}{\partial y'}\right)
\right)
$$
>[!info] First Integral
>The quantity $$f - y'\frac{\partial f}{\partial y'}$$ is defined as the first integral of the Euler-Lagrange equation. When this quantity is constant it implies that the Euler Lagrange equation is zero providing another way to solve these Functional problems.
