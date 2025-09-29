# Transmission Lines
>A transmission line basically consists of two or more **parallel conductors** used to connect a source to a load.

1. It is customary and convenient to describe a transmission line in terms of its **line parameters**, which are its resistance per unit length R, inductance per unit length L, conductance per unit length G, and capacitance per unit length C.
2. The line parameters R, L, G, and C are not **discrete or lumped** but **distributed**
> Lumped = You cannot say, "all the resistance is here, and all the capacitance is there."

![[Pasted image 20250917223227.png]]
> For each line, the conductors are characterized by $\sigma_{c} , \mu_{c},  \epsilon_{c} = \epsilon_{o}$ and the homogeneous dielectric separating the conductors is characterized by $\sigma , \mu,  \epsilon$
>  $G \neq \frac{1}{R}$ *R is the ac resistance* per unit length of the conductors comprising the line and *G is the conductance per unit length* due to the dielectric medium separating the conductors
>  
> 		 $\boxed{LC =\mu \epsilon}$ and $\boxed{\frac{G}{C} = \frac{\sigma}{\epsilon}}$
3. Characteristic Impedance $(Z_{o})$
4. Propagation Constant $(\gamma)$
5. Transverse Electromagnetic (**TEM**) wave
	1. In a TEM wave, **both the electric field (E) and the magnetic field (H)** are **completely transverse (perpendicular)** to the direction of propagation.
	2. Only a two-conductor transmission line supports a TEM wave
6. Lossless Line $(R=0=G)$
	1. A transmission line is said lo be lossless if the conductors of the line are perfect $(\sigma_{c} \approx \infty)$ and the dielectric medium separating them is lossless ($\sigma \approx 0$)
7. Distortionless Line $\left( \frac{R}{L} \right) = \frac{G}{C}$
	1. A distortionless line is one in which the attenuation constant $\alpha$ is frequency independent while the phase constant $\beta$ is linearly dependent on frequency.
$$
\boxed{\frac{R}{L}= \frac{G}{C}}
$$


8. Voltage reflection coefficient ($\Gamma_{L}$)
	1. The voltage reflection coefficient at any point on the line is the ratio of the magnitude of the reflected voltage wave to that of the incident wave.
	2. The current reflection coefficient at any point on the line is negative of the voltage reflection coefficient at that point.
9. Standing Wave Ration (SWR)
10. Telegraphers equation 
11. Input Impedance ($Z_{in}$)
12. Smith chart
	1. . To reduce the tedious manipulations involved in calculating the characteristics of transmission lines