In field theory courses there is a difference between the coordinate derivative and the engineering derivative in terms of units
$$
\frac{\partial V}{\partial x^\mu} \text{ implies different units}
$$
Laplacian on a higher dim vector field can be called the "Hodge Laplacian"

$$
\sum_{n=1}^{\ell} n^2 = 
	\frac{1}{6}\ell(\ell + 1) (2\ell + 1)^{-2}
$$
Which gives an idea as to why we choose a separation coefficient of $\ell(\ell+1)$.

The Legendre Polynomials comes from us focusing on a finite function argument at the ends (which are singular)

Paraxial approximations can be useful for some problems in optics

## Start
---
In general this chapter works with various solutions to Laplace's equation in different coordinate systems. There are a few different coordinate systems where the Laplacian can be separated into different variables. The ones which we will focus on are all **orthogonal systems** whose coordinate axes cross at $90\degree$ angles. Each of these need to have an associated metric which defines how distance works in this particular space. 
$$
ds^2 = \sum_i h_i^2 (dx^i)^2
$$
the values of $h_i$ will depend on the coordinate system that you are working with. The Laplacian separates in the following coordinate systems: plane polars, spherical polars, cylindrical polars, plane elliptic, and three-dimensional ellipsoidal with degenerate limits. The first three are the main ones which are encountered regularly. These typically have the following metrics

| Coordinate System | Corresponding Metric                                       | Corresponding $h$ values                            |
| ----------------- | ---------------------------------------------------------- | --------------------------------------------------- |
| Plane Polar       | $ds^2 = dr^2 + r^2d\theta^2$                               | $h_r=1$, $h_\theta=r$                               |
| Spherical Polar   | $ds^2 = dr^2 + r^2 d\theta^2 + r^2 \sin^2(\theta) d\phi^2$ | $h_r = 1$, $h_\theta = r$, $h_\phi = r\sin(\theta)$ |
| Cylindrical Polar | $ds^2 = dr^2 + r^2 d\theta^2 + dz^2$                       | $h_r = 1$, $h_\theta = r$, $h_z=1$                  |
These metrics can also in theory be found using calc 3 methods but I need to fill out more detail about these first.

## Gradient Operator in Curvilinear Coordinates
---
In order to compensate for this metric we need to take into account the scaling of these distances along each of the coordinates. In particular by representing any displacement in the natural coordinate system any displacement can be represented by $dr = \sum_i h_i dx^i \mathbf{e}_i$. In order to keep the displacement along the gradient to have a consistent definition across coordinate systems the gradient must be defined as follows
$$
\text{grad}(\phi) \equiv
	\nabla\phi = \sum_i \frac{1}{h_i} \left(
		\frac{\partial\phi}{\partial x^i}
	\right) \mathbf{e}_i
$$
This gives two different definitions of the gradient operator depending on the units which you are wanting to work with. The first **physical components** have the $h_i$ components to get them to the same units. While the second are the **coordinate components** which may have different units depending on the setup. 

Using this definitions we can also expand this to define the divergence and gradient in any three dimensional curvilinear coordinate system as follows
$$
\text{div}(A) \equiv \frac{1}{h_1 h_2 h_3} \left(
	\frac{\partial}{\partial x^i}[h_j h_k A_i]
\right)
$$
This is the divergence in Einstein notation
$$
\text{curl}(A)_3 = \frac{1}{h_1 h_2} \left(
	\frac{\partial h_2 A_2}{\partial x^1} - 
	\frac{\partial h_1 A_2}{\partial x^2}
\right)
$$
The rest of the components can be found using a cyclic ordering of coordinates as $1 \rightarrow 2 \rightarrow 3 \rightarrow 1$. Similarly the Laplacian can also be defined in this way as follows
$$
\nabla^2 \varphi = \frac{1}{h_1 h_2 h_3} \left\{
	\frac{\partial}{\partial x_i} \left(
		\frac{h_j h_k}{h_i} \frac{\partial \varphi}{\partial x_i}
	\right)
\right\}
$$
This is also in Einstein notation.
>[!warning] Vector field Laplacian
>The Laplacian of curvilinear coordinates is different depending on if you are dealing with a vector field. If you are dealing with a vector field then you need to use the *vector laplacian* which is defined as follows
>$$\nabla^2 \mathbf{A} = \text{grad div}(A) - \text{curl curl}(A)$$

## Spherical Harmonics
---
