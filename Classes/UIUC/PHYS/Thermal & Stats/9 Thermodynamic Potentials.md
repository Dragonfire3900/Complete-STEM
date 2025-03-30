Tags: #raw #ThermoStats #Theory
Related: [[Lect9.pdf|PHYS 427 Lecture 9]]
- --
In thermodynamics there are many different properties you can measure and work with. Previously we defined a few different concepts in the pressure, temperature, and internal energy. Each of these we have a rough intuitive idea of what these mean/look like. 
- Pressure: how much force per unit area something exerts
- Temperature: Roughly related to the internal energy through the [[6 Equipartition Theorem|equipartition theorem]] but defined using the entropy
- Internal energy: How much energy it takes to make a system

However we also introduced the [[7 Helmholtz Free Energy|Helmholtz free energy]] ($F$) when talking about the canonical ensemble. But what does this really mean and why does it take the form it does? It turns out **there is a class of quantities** called the thermodynamic potentials which relate to the amount of energy stored in the system. The Helmholtz free energy is one of these potentials.

# Interpreting Potentials
---
It was mentioned before the Helmholtz free energy has the following form
$$\Huge
	F = U - TS
$$
Each of the different potentials describe how much energy it takes to assemble a system but in different circumstances. The Helmholtz free energy assumes the [[5 Canonical Ensemble|canonical ensemble]] (<font color="red">at some constant temperature and volume</font>) which means that we can exchange heat between the reservoir and the system. Effectively we can also absorb heat $Q = T\Delta S$ from the reservoir in order to make it easier to assemble the system; thereby decreasing the amount of energy required. This would be the Helmholtz free energy and also why it has the $TS$ term subtracted away.

We can imagine many other systems and different forms of energy we can add/remove from them. This would provide a **unique set of energies required in order to make a system** which is what each of the thermodynamic potentials are. There are a few which are important to our studies

# Useful Potentials
---
For each of these potentials there is some definition which usually relates to the internal energy of the system and a differential form which shows how this potential changes under different circumstances. In particular it suggests the natural variables which the potential is a function of.
> [!note]+ Internal Energy ($\large U$)
> We've encountered this one before and it's the raw amount of energy required to assemble a system assuming no outside influence. It can be calculated from the partition function itself using the following
> $$\huge \langle U \rangle = -\partial_{\beta} \ln(Z)$$
> It also has the following differential relationship from the fundamental thermodynamic identity
> $$\huge dU = TdS - pdV$$
> It's natural variables are the entropy $S$ and the volume of the system $V$

> [!note]+ Helmholtz Free Energy ($\large F$)
> We've also seen this one before and it assumes the canonical ensemble at some **constant temperature and volume**. It represents the amount of energy required to build the system while absorbing some heat from the reservoir. It has the following definition in terms of the internal energy
> $$\huge F = U - TS$$
> and the following differential form (following the differential form of the internal energy)
> $$\huge dF = -SdT - pdV$$
> It's natural variables are the temperature and volume

> [!note]+ Enthalpy ($\large H$)
> This describes the amount of energy required to assemble a system in an atmosphere unconnected to any reservoir. In assembling the system you have to displace the gas, which does work thereby increasing the amount of energy required. It has the following definition in terms of internal energy
> $$\huge H = U + pV$$
> and the following differential form
> $$\huge dH = TdS + Vdp$$
> It's natural variables are the entropy and pressure

>[!note]+ Gibbs Free Energy ($\large G$)
>This is a pressurized system attached to some reservoir meaning that we can absorb some heat from it to make things easier. Essentially this is the enthalpy plus a little bit. It has the following definition in terms of internal energy
>$$\huge G = U + pV - TS$$
>and the following differential form
>$$\huge dG = -SdT + Vdp$$
>It's natural variables are the temperature and pressure

Notice how each of these have natural variables (defined by their differential relationships). These natural variables suggest when a specific potential would be useful to work with/know. For example the Gibbs free energy is typically used when the temperature and pressure are constant which would include most chemical reactions!

Also notice how these natural variables come in pairs with one another (pressure is always with volume and entropy is always with temperature). In both cases one of these is extensive and the other is intensive. These are examples of many different [conjugate variables](https://en.wikipedia.org/wiki/Conjugate_variables_(thermodynamics)) which always come in these pairs and they have units of energy when multiplied together. You can think of each of these pairs as generalized "forces" (intensive quantity) and generalized "displacements" (extensive quantity).

# Maxwell Relations
---
In mathematics there is a theorem which states that the order in which you take a partial derivative doesn't matter. I.E.
$$\large
	\frac{\partial^2 f}{\partial x \partial y} =
	\frac{\partial^2 f}{\partial y \partial x}
$$
We can apply this same idea to the differential forms of the various thermodynamic potentials to get relationships between various partial derivatives. These are call the Maxwell relationships and there are quite a few of them. The main ones we'll end up dealing with are the following
$$\large\begin{gather}
	\frac{\partial^2 U}{\partial S \partial V} =
		\left(\frac{\partial T}{\partial V}\right)_{S} =
		-\left(\frac{\partial p}{\partial S}\right)_{V} \\
	-\frac{\partial^2 F}{\partial T \partial V} = 
		\left(\frac{\partial S}{\partial V}\right)_{T} =
		\left(\frac{\partial p}{\partial T}\right)_{V} \\
	\frac{\partial^2 H}{\partial p \partial S} = 
		\left(\frac{\partial T}{\partial p}\right)_{S} =
		\left(\frac{\partial V}{\partial S}\right)_{p} \\
	-\frac{\partial^2 G}{\partial p \partial T} = 
		\left(\frac{\partial S}{\partial p}\right)_{T} =
		-\left(\frac{\partial V}{\partial T}\right)_{p} \\
\end{gather}$$
But these can be kind of hard to remember off the top of your head. Instead there is a visual tool to help you remember them!
## Thermodynamic Square
---
The thermodynamic square is a visual tool to help you remember the Maxwell relationships and the main thermodynamic potentials. This isn't in the lectures but I found out about it through the [wikipedia article](https://en.wikipedia.org/wiki/Thermodynamic_square) about it. Visually the square looks like the following

|      $\huge -S$      | $\color{red}\huge U$ |      $\huge V$       |
| :------------------: | :------------------: | :------------------: |
| $\color{red}\huge H$ |                      | $\color{red}\huge F$ |
|      $\huge -p$      | $\color{red}\huge G$ |      $\huge T$       |
This single table encodes pretty much everything you'd need to know about these four different thermodynamic potentials
>[!note]- Derivative relations (Ex: $\large U$)
>You can find the differential relationships for the different potentials by doing the flowing
>1. Put yourself at the potential of interest. For us this would be U
>2. Look at the opposite two corners. These two corners would give you the coefficients for the differential quantities. In this case that would be $-p$ and $T$
>3. Look at the corners next to the potential. These two corners are the differential component for this potential. The corner along a straight line corresponds with the previous coefficient. In our example this would be $S$ and $V$. Note that sign only affects the coefficient
>4. Add the chemical potentials $\mu$ and $dN$ to get the final result!

>[!note]- Maxwell relations
>This square also encodes all of the normal Maxwell relationships! This is a bit stranger though. In general you can trace out "L" blocks and mirrored "L" blocks along the edge of the square. When combined together these can make a rotated "U" shape. This "U" represents the corresponding Maxwell relationship with the two "L" blocks being the two sides. The partial derivative is always taken along the long edge of the U shape while what's held constant is the ending corner.

