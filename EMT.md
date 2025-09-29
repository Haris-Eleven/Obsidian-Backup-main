![[Pasted image 20250923020527.png]]
![[Pasted image 20250917223227.png]]
![[Pasted image 20250917232556.png]]	     $\boxed{LC =\mu \epsilon}$ and $\boxed{\frac{G}{C} = \frac{\sigma}{\epsilon}}$

- 1 $\frac{Np}{m}$ = 8.686 $\frac{dB}{m}$
- 
# General Solution of Transmission Line
![[Pasted image 20250918020152.png]]
- From KVL & KCL
$$
\boxed{\begin{aligned}
\frac{dV_s(z)}{dz} &= -\bigl(R + j\omega L\bigr)\,I_s(z) \\[6pt]
\frac{dI_s(z)}{dz} &= -\bigl(G + j\omega C\bigr)\,V_s(z)
\end{aligned}}
$$
- using above equations
$$
\begin{aligned}
\frac{d^2 V_s(z)}{dz^2} &= \bigl(R + j\omega L\bigr)\,\bigl(G + j\omega C\bigr)\,V_s(z) \\[6pt]
\frac{d^2 I_s(z)}{dz^2} &= \bigl(R + j\omega L\bigr)\,\bigl(G + j\omega C\bigr)\,I_s(z)
\end{aligned}
$$
- In terms of $\gamma$  *Propagational constant*
$$
\gamma = \sqrt{ \bigl(R + j\omega L\bigr)\,\bigl(G + j\omega C\bigr) }
$$
- Transmission line equation (**Voltage Wave** and **Current Wave**)
$$
\begin{aligned}
\frac{d^2 V_s(z)}{dz^2} &= \gamma^2\,V_s(z) \\[6pt]
\frac{d^2 I_s(z)}{dz^2} &= \gamma^2\,I_s(z)
\end{aligned}
$$
> For a second order differential equation with roots $a,b$ the general solution is given by:

$$
\boxed{y(z) = C_1 e^{az} + C_2 e^{bz}, \quad \text{for distinct roots } a \neq b}
$$
- Solution for voltage wave:
$$
V_s(z) = V_0^+ e^{-\gamma z} + V_0^- e^{+\gamma z}
$$
- **Telegrapher's Equation**
$$
\boxed{I_s(z) = I^+(z) + I^-(z)
= \frac{V_0^+}{Z_0} e^{-\gamma z} \;-\; \frac{V_0^-}{Z_0} e^{+\gamma z}.}
$$

- $V_{o}^+$​: amplitude of the forward (incident) wave.
    
- $V_{o}^-$​: amplitude of the backward (reflected) wave.

# Characteristic Impedance  $(Z_{o})$
Ration of *forward travelling voltage* to *forward travelling current* wave at any point
$$
Z_{0} = \frac{V_{0}^{+}}{I_{0}^{+}}
$$
$$
Z_0 = \sqrt{\frac{R + j\omega L}{G + j\omega C}} = \frac{{R+j\omega L}}{\gamma} = \frac{\gamma}{G+ j\omega C}
$$

# Lossless Transmission 
Condition : $R= 0 \text{ and } G=0$
$$
\gamma = \sqrt{(R + j\omega L)(G + j\omega C)} = \alpha + j\beta
$$
$$
\begin{aligned}
\gamma &= j\beta,\qquad \alpha = 0,\\[4pt]
\beta  &= \omega\sqrt{LC},\\[4pt]
Z_0   &= \sqrt{\frac{L}{C}}\quad\text{(for lossless line).}
\end{aligned}
$$
- Primary Constants in terms of secondary 
$$
R = 0, \quad G = 0, \quad
L = \frac{\beta Z_0}{\omega}, \quad
C = \frac{\beta}{\omega Z_0}.
$$

# Distortionless Transmission
Condition: 
$$
\frac{R}{L}= \frac{G}{C}
$$
$$
\boxed{
\alpha = \sqrt{RG}, \quad
\beta = \omega \sqrt{LC}, \quad
Z_0 = \sqrt{\tfrac{L}{C}}, \quad
v_p = \frac{1}{\sqrt{LC}}
}
$$
$$
\boxed{
\begin{aligned}
R & = \alpha\,Z_0, 
\qquad &L &=\frac{\beta Z_0}{\omega},\\[6pt]
G &=\frac{\alpha}{Z_0},
\qquad &C &= \frac{\beta}{\omega Z_0}.
\end{aligned}
}
$$
# Reflection Coefficient:
![[Pasted image 20250918140018.png]]
$$
\begin{aligned}
V_s(\ell) &= V_0^+ e^{-\gamma\ell} + V_0^- e^{+\gamma\ell},\\[4pt]
I_s(\ell) &= \dfrac{V_0^+}{Z_0} e^{-\gamma\ell} - \dfrac{V_0^-}{Z_0} e^{+\gamma\ell}.
\end{aligned}
$$

$$
\Gamma_L \equiv \frac{V_0^- e^{+\gamma\ell}}{V_0^+ e^{-\gamma\ell}}
= \frac{Z_L - Z_0}{Z_L + Z_0}.
$$
$$
\boxed{\Gamma_L \;=\; \dfrac{Z_L - Z_0}{Z_L + Z_0}}
$$
$$
\boxed{\Gamma_{d} = \Gamma_{L}e^{-2j\beta l}}
$$
- Ideal transmission line has reflection coefficient = 0
# VSWR
![[Pasted image 20250923103103.png]]
Due to interference between forward and reverse wave
$$
\mathrm{S} \;=\; \frac{V_{\max}}{V_{\min}}.
$$
$$
\mathrm{S} \;=\; \frac{1 + |\Gamma|}{1 - |\Gamma|}.
$$
$$
Z_{\max} = Z_0 \, S
$$
$$
Z_{\min} = \frac{Z_0}{S}
$$
# Input Impedance:
![[Pasted image 20250918140018.png]]
- Voltage and current at input side
![[Pasted image 20250923111433.png]]
![[Pasted image 20250918143517.png]]
![[Pasted image 20250918143544.png]]
![[Pasted image 20250918144354.png]]
![[Pasted image 20250918144426.png]]
$$
\boxed{\,Z_{\mathrm{in}}
=Z_0\,\frac{Z_L + Z_0\tanh(\gamma\ell)}{Z_0 + Z_L\tanh(\gamma\ell)}\,}
$$
![[Pasted image 20250918145056.png]]
$$
 \beta l = \text{Electrical Length}
$$
- If $\beta l \to \infty$ $Z_{in} = \frac{Z_{o}^2}{Z_{l}}$
1. Shored Line ($Z_{L} = 0$)
2.  Open - Circuited Line ($Z_{L} = \infty$)
3. Matched Line ($Z_{L} = Z_{o}$)
# Smith Chart: 
- A graphical method to calculate
![[Pasted image 20250918145918.png]]
Unit circle on which the smith chart is constructed
$$
\begin{aligned}
\Gamma &= \frac{Z-Z_0}{Z+Z_0}, \qquad z=\frac{Z}{Z_0}=r+jx,\\[6pt]
\Gamma &= \frac{z-1}{z+1}=\frac{(r+jx)-1}{(r+jx)+1},\quad \Gamma=\Gamma_{r}+j\Gamma_{i},\\[6pt]
\end{aligned}
$$
- simplifying for gamma real and img

$$
z_L = r + jx = \frac{1 + \Gamma}{1 - \Gamma}, \quad \Gamma = \Gamma_r + j \Gamma_i
$$
$$
\begin{aligned}
\text{Constant resistance (r)} &: (\Gamma_r - \frac{r}{1+r})^2 + \Gamma_i^2 = (\frac{1}{1+r})^2\\[1mm]
\text{Constant reactance (x)} &: (\Gamma_r - 1)^2 + (\Gamma_i - \frac{1}{x})^2 = (\frac{1}{x})^2
\end{aligned}
$$

- r - circles:
 ![[Pasted image 20250918153616.png]]
 - x- circle
 ![[Pasted image 20250918231450.png]]
- A complete revolution (360°) around the Smith chart represents a distance of $\lambda$/2 on the line
- Clockwise movement on the chart is regarded as moving toward the generator (or away from the load)  Similarly, counterclockwise movement on the chart corresponds to moving toward the load.
# Impedance to admittance transformation
# Impedance Matching 

-----
----
# Fundamentals & Equations
![[Pasted image 20250922195047.png]]
## Lorentz Force  
- Force on a charged particle in electric and magnetic fields.  
- Equation:  
$$\vec{F} = q\left(\vec{E} + \vec{v} \times \vec{B}\right)$$  

---

## Del Operator  
- A vector differential operator.  
- Definition:  
$$\nabla = \hat{i}\frac{\partial}{\partial x} + \hat{j}\frac{\partial}{\partial y} + \hat{k}\frac{\partial}{\partial z}$$  

---

## Gradient of $\phi$  
- Points in direction of maximum increase of scalar field $\phi$.  
- Equation:  
$$\nabla \phi = \frac{\partial \phi}{\partial x}\hat{i} + \frac{\partial \phi}{\partial y}\hat{j} + \frac{\partial \phi}{\partial z}\hat{k}$$  

---

## Divergence of $\vec{A}$  
- Measures net "outflow" of vector field $\vec{A}$.  
- Equation:  
$$\nabla \cdot \vec{A} = \frac{\partial A_x}{\partial x} + \frac{\partial A_y}{\partial y} + \frac{\partial A_z}{\partial z}$$  

---

## Curl of $\vec{A}$  
- Measures local rotation of vector field $\vec{A}$.  
- Equation:  
$$\nabla \times \vec{A} = 
\begin{vmatrix}
\hat{i} & \hat{j} & \hat{k} \\
\frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
A_x & A_y & A_z
\end{vmatrix}$$  

---

## Vector Field  
- A function that assigns a vector to every point in space.  
- Example:  
$$\vec{F}(x,y,z) = x\hat{i} + y\hat{j} + z\hat{k}$$---
## Cylindrical Coordinate System  
![[Pasted image 20250922195407.png]]
- Coordinates: $(r, \phi, z)$.  
- Unit vectors:  
  - $\hat{a}_r$: radial outward  
  - $\hat{a}_\phi$: tangential (direction of increasing $\phi$)  
  - $\hat{a}_z$: along $z$-axis  

---

## Spherical Coordinate System 
![[Pasted image 20250922200900.png]]
- Coordinates: $(r, \theta, \phi)$  
- Unit vectors:  
  - $\hat{a}_r$: radial outward  
  - $\hat{a}_\theta$: polar (down from $z$-axis)  
  - $\hat{a}_\phi$: azimuthal (around $z$-axis)  

---

## Constant Coordinate Surface  
- Surfaces formed by holding one coordinate fixed.  
- Examples:  
  - Cylindrical: $r=\text{constant}$ is a cylinder.  
  - Spherical: $r=\text{constant}$ is a sphere.  

---

## Line Integral  
- Integral of a field along a path.  
- Equation:  
$$\int_C \vec{F} \cdot d\vec{l}$$  

---

## Surface Integral  
- Flux of a vector field through a surface.  
- Equation:  
$$\iint_S \vec{F} \cdot d\vec{S}$$  

---

## Volume Integral  
- Integral of a function over a volume.  
- Equation:  
$$\iiint_V f(x,y,z)\, dV$$  

---

## Gauss's Divergence Theorem  
- Converts flux through surface into volume divergence.  
- Equation:  
$$\iint_S \vec{F}\cdot d\vec{S} = \iiint_V (\nabla \cdot \vec{F})\, dV$$  

---

## Stokes Theorem  
- Converts circulation around boundary into curl over surface.  
- Equation:  
$$\oint_C \vec{F}\cdot d\vec{l} = \iint_S (\nabla \times \vec{F}) \cdot d\vec{S}$$  

---

## Laplacian of a Scalar  
- Divergence of the gradient.  
- Equation:  
$$\nabla^2 \phi = \frac{\partial^2 \phi}{\partial x^2} + \frac{\partial^2 \phi}{\partial y^2} + \frac{\partial^2 \phi}{\partial z^2}$$  

---

## Gauss's Law  
- Electric flux through closed surface = enclosed charge / $\epsilon_0$.  
- Equation:  
$$\iint_S \vec{E}\cdot d\vec{S} = \frac{Q_{\text{enc}}}{\epsilon_0}$$
$$\int_S \vec{E}\cdot d\vec{S} = \frac{Q_{\text{enc}}}{\epsilon_0}$$

---

## Maxwell's Equations  

1. **Gauss’s Law (Electric field):**  
$$\nabla \cdot \vec{E} = \frac{\rho}{\epsilon_0}$$  

2. **Gauss’s Law (Magnetic field):**  
$$\nabla \cdot \vec{B} = 0$$  

3. **Faraday’s Law:**  
$$\nabla \times \vec{E} = -\frac{\partial \vec{B}}{\partial t}$$  

4. **Ampère–Maxwell Law:**  
$$\nabla \times \vec{B} = \mu_0 \vec{J} + \mu_0\epsilon_0 \frac{\partial \vec{E}}{\partial t}$$  
