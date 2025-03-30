- --
Precise descriptions of thermal properties requires combinatorics and the ability to count how things are arranged. We will use this to describe how things work!
# Microstates & Macrostates
- --
The first thing to distinguish between are microstates and macrostates. Colloquially the microstate is a set of variables describing "everything" within the system while the macrostate are a small set of properties which describe the whole system. Relating these two is the essence of thermal and statistical mechanics. 

>[!info]- Ex: Box of gas
>A box of full of $N$ gas particles has the following description
>- Microstate: The phase space of all particles such as position and momentum ($\left\{\left(x_i, p_i\right) \;\forall  \;i\right\}$)
>- Macrostate: Gas pressure, Avg. kinetic energy, etc.

>[!info]- Ex: Polymer
>- Microstate: "config" of each atom and the bonds.
>- Macrostate: Typical size of the polymer, end to end length

The most useful thing to initially describe is a two state system because we can apply two-state combinatorics. We can use this type of system to show that with proper definition knowing the microstate maps to a macrostate but not the reverse.
$$
\large
\exists F: \text{microstate} \rightarrow \text{macrostate},
\nexists G: \text{macrostate} \rightarrow \text{microstate}
$$
This gives rise to the idea of **multiplicity** which gives the number of microstates that correspond to a particular macrostate. In general, the macrostate is typically described by the total energy of the system.

# Einstein Solids
---
This is a way of modeling the thermodynamic properties of a cold solid. It assumes that the solid is made of independent particles each of which act as a quantum harmonic oscillator. These oscillations can occur in any direction and thus each particle is characterized by three independent oscillators. This is referred to as an Einstein solid. These solids have the following multiplicity
$$
	\huge
	\Omega(N,q) = {q+N-1\choose q} = \frac{\left(q+N-1\right)!}{q!\left(N-1\right)!}
$$
This can be shown by imagining the system as a set of dots (for energy) and partitions (for the different oscillators). We can rearrange these systems based on their position but also based on the individual units of partitions/dots. Which gives rise to the formula above.

# Interacting Systems
---
In order to understand heat and irreversible processes we need to understand how energy can be exchanged between systems. In order to examine this we will look at **weakly coupled** systems whose exchange of energy between the systems is much slower than the exchange for individual parts.