1. *Why Sinusoid is considered in Fourier Series*
	`Because of Orthogonality, think in terms of vector representation, any n dimensional vector can be represented by n orthogonal vectors without any error `
	`sine and its harmonics are orhtogonal same goes for cosines`
	![[Pasted image 20250907164446.png]]
2. SNR: $\frac{P_{s}}{P_{n}}$ ratio of signal power and Noise power
3. If a signal $g(t)$ is approximated by another signal $x(t)$ as $g(t) = cx(t)$ then the optimum value of $c$ that minimizes the energy of the error signal is given by what expression ?
$$ e_x(t) = g(t) - c*x(t)$$
$$\frac{dE_e(t)}{dt} = 0$$
$$ c = \frac{1}{E_x}\int_{t_1}^{t_2}g(t) x(t)dt$$
$$ c = \frac{1}{E_x}\int_{t_1}^{t_2}g(t) x^*(t)dt$$
- For error to be minimum $x(t) \text{ and } g(t)$ must be orthogonal, which is only possible for sinosoid and exponential.
1. Orthogonal vs Orthonormal 
` when you average their overlap over the whole interval, it cancels out exactly`
2. In case of complex signals the definition of orthogonality is: 
$$ \int_{t_1}^{t_2}g(t) x^*(t)dt =\int_{t_1}^{t_2}g^*(t) x(t)dt = 0 $$
---
![[Pasted image 20250907163514.png]]
# Fourier Series 
**Fourier Series says:**
> Any **periodic signal** (no matter how complicated) can be expressed as a weighted sum of sines and cosines of different frequencies.
> $a_n \  b_n$ are Fourier coefficients → tell you how much of each harmonic is present.
> $\omega_o$ is the fundamental frequency, rest are harmonics. 
$$
X(t) = \sum_{-\infty}^{\infty} x_ne^{-j\omega_nt}
$$
- How to find these coefficients 
## Parseval's Theorem
- Total avg power in time domain is equal to the sum of square of magnitude of its fourier series coefficients in frequency domain.
---

# Fourier Transform 
**Fourier Transform says:**
> Any (reasonable) signal can be represented as a continuous mixture of sinusoids at all possible frequencies.
> Now you can’t just use discrete harmonics (fixed multiples of one frequency).
   Instead, you need a **continuum of frequencies**

1.  Dirchlet's Condition
2. Properties of F.T 
3. The signal is made periodic using impulse train 
4. Contribution of each orthogonal sine and cosine component
![[Pasted image 20250919152540.png]]
![[Pasted image 20250907164753.png]]
$$\mathcal{F}\{\cos(\omega_0 t)\} = \tfrac{1}{2}\Big[\delta(f - f_0) + \delta(f + f_0)\Big], \quad f_0 = \frac{\omega_0}{2\pi}$$
$$\mathcal{F}\{\sin(\omega_0 t)\} = \tfrac{1}{2j}\Big[\delta(f - f_0) - \delta(f + f_0)\Big], \quad f_0 = \frac{\omega_0}{2\pi}$$

$$\mathcal{F}\{m(t)\cos(4\pi f_c t)\}
=\tfrac{1}{2}\,M(f-2f_c)+\tfrac{1}{2}\,M(f+2f_c)$$
$$\mathcal{F}\{e^{j\omega_0 t}\} = 2\pi \, \delta(\omega - \omega_0)$$
$$\mathcal{F}\{e^{j 2\pi f_0 t}\} = \delta(f - f_0)$$


### Duality Property
$$g(t) \leftrightarrow G(f)$$
$$ G(t) \leftrightarrow g(-f) $$
---
$$X(\omega) = \int_{-\infty}^\infty x(t)e^{-i\omega t}dt$$
$$x(t) = \frac{1}{2\pi}\int_{-\infty}^{\infty}X(\omega) e^{i\omega t}d\omega $$
## Frequency Transform Theorem 
	or Modulation Theorem 
If
$$ x(t) \leftrightarrow X(f) $$
then multiplying $x(t)$ by a **complex exponential** shifts the spectrum:
$$x(t)*e^{2\pi f_ct} = X(f-f_c)$$
#question How can an aperiodic signal have a frequency? 
- ***The main idea is that we are talking in terms of sinusoids, that how can we represent the function in terms of a sinusoid***.
---
# Key Terms:
1. Base band Signal: Message Signal (near 0Hz )
2. Band Pass Signal: Message Signal * exponential
# LTI
An LTI system is completely described by its impulse response $h(t)$ 
# Convolution 
Sliding, flipping, and multiplying process.
# [Hilbert Transform](https://www.youtube.com/watch?v=0PyLguMXRfc&list=PLwjK_iyK4LLArUHRm3SvPLT0XWlVhpl4h&index=22&t=812s)
Shifts the phase of every frequency component by $- 90\degree$ 
$$
\hat{x}(t) = \mathcal{H}\{x(t)\} = \frac{1}{\pi} \; \text{P.V.} \int_{-\infty}^{\infty} \frac{x(\tau)}{t-\tau} \, d\tau
$$
- This is the convolution of $x(t)$ with $\frac{1}{\pi t}$ 
- Frequency domain conversion is done by using duality property
P.V: Cauchy principal value
In frequency domain:
$$\hat{X}(f) =
\begin{cases}
-j X(f), & f > 0 \\
+j X(f), & f < 0 \\
0, & f = 0
\end{cases}
$$
or 
$$\hat{X}(f) = -jsgn(f)X(f)$$
$$sgn(\omega) \leftrightarrow \frac{1}{j\pi t} $$
1. $F({e^{j2\pi f_ot}}) = \delta{(f-f_o)}$
## Analytic Representation 
The **analytic signal** of a real signal $x(t)$ is defined as:  $$z(t) = x(t) + j \hat{x}(t)$$
- It represent the envelop of $x(t)$ for all kinds of signal

$$Z(f) =
\begin{cases}
2X(f), & f > 0 \\
X(0), & f = 0 \\
0, & f < 0
\end{cases}$$
### Envelope Representation
$$A(t) = |z(t)| = \sqrt{x(t)^2 + \hat{x}(t)^2}
$$
**Physical meaning**: The envelope is the **outer curve** that shows how the amplitude of a fast oscillating signal varies with time.
- To represent only the +ve frequency component: 
	- $X_p(f) = {X(f) + jX_h(f)}$
### Complex Envelop Representation
$$

z(t) = x(t) + j \hat{x}(t) = u(t) e^{j 2\pi f_c t}

$$
$u(t)$ is the complex envelop 

# Fundamental of Analog Signal Transmission
$$x(t) \rightarrow h(t) \rightarrow + n(t) \rightarrow y(t) $$
- Only frequencies within the range of Bandwidth can pass without sever attenuation. 
## Distortion:
Ideal Channel Condition: 
1. Magnitude Condition: Within the signal’s bandwidth, the **magnitude response** of the channel must be constant
	- If this isn't the case then **Amplitude Distortion** 
$$|H_c(f)| = K \quad \text{for } |f| \leq B$$
2. Phase Condition: The **phase response** of the channel must be linear in frequency:
$$\angle H_c(f) = -2\pi f \tau$$
	- If not equal then **Phase Distortion** also called **Delay Distortion**, removed by an equipment called *Equalizer*.
$$H_{eq}(f)H_c(f) = K e^{-j2\pi f \tau} \quad \text{for } |f| \leq B$$
3. Combined Ideal Condition:
$$H_c(f) = K e^{-j2\pi f \tau} \quad \text{for } |f| \leq B
$$
---
1. Linear Distortion: If system is LTI but distortion less condition is not followed 
2. Non-Linear Distortion: Not LTI, additional frequency components are present, This additional frequency is called **Intermodulation distortion** or **Harmonic Distortion**
3. **Cross talk/ co channel interference**
## Modulation
Why Modulate?
We can’t transmit $m(t)$ directly over long distances because:
- Antennas for very low frequency signals would be HUGE. $AntennaSize \propto \frac{1}{f}$
- Multiple baseband signals would interfere (all start from 0 Hz).
So, we **shift** the spectrum up to a high frequency, called the **carrier frequency** $f_c$​.
- Multiplication of two signals is called mixing or heterodining operation
---

1. Baseband Communication
2. Carrier Communication
### DSB SC
#### Modulation
A **sideband** is simply the **copy of the message spectrum** that appears around the carrier frequency after modulation.
Double Side Band Suppressed Carrier (DSB-SC): **Simplest type of Modulation** $$s(t)= m(t).c(t)$$where, $c(t) = cos(2\pi f_ct)$ is **high frequency** cosine. 
	$\frac{f_c}{\beta} = 100-300$
	$$S(f) = \tfrac{1}{2} \Big[ M(f - f_c) + M(f + f_c) \Big]
	$$
![[Pasted image 20250907165523.png]]![[Pasted image 20250907165736.png]]
This means:
- The original spectrum $M(f)$ is **shifted up** to be centered at $+f_c$
]
-  And also **mirrored** and shifted to $-f_c$
- $fc \geq\beta$ else overlap will happen
- Bandwidth of message signal = $\beta$
- B.W of DSB-SC signal = $2\beta$
#### Demodulation
1. Synchronous Modulation & Coherent Detection
2. Effect of loss of coherence:
	- After Passing through LPF $$
\hat{m}(t) = \frac{1}{2}\cos(\theta)m(t)
$$
### DSB With Carrier
![[Pasted image 20250906162233.png]]
$\phi_{AM}(t) =A_{c}Cos(\omega_{c} t) + m(t)A_{}Cos(\omega_{c}t)$
$A_{c}+ m(t) \geq = 0$
1. Modulation Index : For tone modulation  $(\mu) = \frac{A_{m}}{A_{c}}= \frac{{e(t)_{max}-e(t)_{min}}}{e(t)_{max}+e(t)_{min}}$
![[Pasted image 20250907171140.png]]2. For this kind of modulation $\mu \leq 1$
$\eta = power efficiency = \frac{usefulPower}{TotalPower}$
2. $\eta = \frac{\mu^{2}}{\mu^{2}+2}$
3. Sideband power $P_{sb} = \frac{A_{c}^2*\mu^{2}}{4}$
4. Carrier Power $P_{c} = \frac{A_{c^{2}}}{2}$
5. Total Power $P_{t} = P_{c}\left( 1+ \frac{\mu^{2}}{2} \right)$ can also be represented as $P_{t} = \frac{m^{2}(t)}{2} + \frac{A_{c}^{2}}{2}$
#### Demodulation
Envelope detection 
![[Pasted image 20250906161739.png]]
 $\frac{1}{f_{c}} \ll (R_{l}+ R_{s})C \ll \frac{1}{f_{m}}$
### QAM
- Transmitting two DSB s/g using carrier of same frequency but in phase quadrature. 
$$
 \phi_{AM}(t) = {A_{1}M_{1}(t)\cos \omega _{c}t} + A_{1}M_{2}(t)\sin \omega_{c}t
$$

### SSB 
![[Pasted image 20250907173042.png]]
$$
\phi_{USB}(f) = M_{+}(f-f_{c}) + M_{-}(f+f_{c})
$$
Using **Hilbert Transform**:
$$
\phi_{USB}(f) = \frac{1}{2}[M(f-f_{c})+ jM_{h}(f-f_{c})] + \frac{1}{2}[M(f+f_{c})- jM_{h}(f+f_{c})]
$$
Using frequency shifting property of F.T:
$$
 \phi_{USB}(t) = m(t)\cos(\omega_{c}t) - m_{h}(t)\sin(\omega_{c}t)
$$
$\text{Inphase Component} = \cos \omega_{c}t$
$\text{Quadrature Component} = \sin \omega _ct$
- *Demodulation* is done the same way as for DSB-SC
- Method 2 for ***demodulation*** is SSB with carrier or **carrier reinsertion** method.

### VSB
![[Pasted image 20250907181014.png]]  
>If DC or low frequency component it is difficult to generate SSB 
   *VSB Filter*
![[Pasted image 20250907181142.png]]![[Pasted image 20250907181319.png]]
### Phase Modulation:
- Carrier Signal:
$$s_c(t) = A_c \cos(\omega_c t + \phi_c)$$
- Phase modulation:
$$s_{PM}(t) = A_c \cos\big(\omega_c t + k_p\, m(t)\big)$$
- Frequency modulation:
$$\omega_i(t) = \omega_c + k_f\, m(t)$$

$$s_{FM}(t) = A_c \cos\!\Big(\omega_c t + k_f \int_{0}^{t} m(\tau)\, d\tau \Big)$$
$$\theta_i(t) = \omega_c t + \phi(t),\qquad
\omega_i(t) = \frac{d\theta_i(t)}{dt}$$
- Analysis using sinusoidal message:
$$s_{PM}(t) = A_c \cos\!\big(\omega_c t + k_p A_m \cos(\omega_m t)\big)$$

- The PM modulation index:
$$\beta_{PM} \triangleq k_p A_m$$

$$s_{PM}(t) = A_c \cos\!\big(\omega_c t + \beta_{PM}\cos\omega_m t\big)$$
- Frequency modulation using sinusoid:
$$\phi(t) = k_f \int_0^t A_m \cos(\omega_m \tau)\,d\tau
= \frac{k_f A_m}{\omega_m}\sin(\omega_m t)$$

$$\beta_{FM} \triangleq \frac{k_f A_m}{\omega_m} = \frac{\Delta f}{f_m}$$

$$s_{FM}(t) = A_c \cos\!\big(\omega_c t + \beta_{FM}\sin\omega_m t\big)$$
- Using fourier transform: where $J_{n}(\beta)$ is the Bessel Function of the first kind
$$s_{FM}(t) = A_c \sum_{n=-\infty}^{\infty} J_n(\beta)\cos\big(\omega_c t + n\omega_m t\big)$$
- Bandwidth of FM is infinite theoretically 
Important properties of Bessel Function:
1. Narrowband approximations ($\beta \ll 1$)
$$s_{FM}(t) \approx A_c \big[\cos\omega_c t - \beta \sin\omega_c t \sin\omega_m t\big]$$

$$s_{FM}(t) \approx A_c\cos\omega_c t + \frac{A_c\beta}{2}\big(\cos(\omega_c+\omega_m)t - \cos(\omega_c-\omega_m)t\big)$$
This shows three main components (carrier + 2 first-order sidebands)
2. Bandwidth estimates using Carson's Rule: 
	$$BW \approx 2\big(\Delta f + f_m\big) = 2 f_m (\beta + 1)$$
3. Power 
$$P_{inst} = \frac{A_c^2}{2}$$

$$P_{avg} = \frac{A_c^2}{2}$$
4. Power ratio
   $$
\frac{\frac{1}{2}A^{2}J_{n}(\beta)^{2}}{\frac{1}{2}A^{2}}
$$
5. Relationships bw the two
$$\phi_{PM}(t) = k_p m(t) \quad\text{(PM)}$$
$$\phi_{FM}(t) = k_f \int_0^t m(\tau)\,d\tau \quad\text{(FM)}$$

Hence
$$\text{PM}\{m(t)\} \equiv \text{FM}\{\dot m(t)\}\quad\text{(up to scaling)}$$
$$\text{FM}\{m(t)\} \equiv \text{PM}\{\int m(t)dt\}\quad\text{(up to scaling)}$$
### Superheterodyne Receiver 
Processing cost of circuit is high at high frequency

$$
P_{SB} = \frac{1}{2}m^2(t)
$$
here $m^2(t)$ is the average of the square of input signal over one time period.

$$\cos(c+d) = \cos c \cos d - \sin c \sin d$$
$$\cos(c-d) = \cos c \cos d + \sin c \sin d$$

$$\sin(c+d) = \sin c \cos d + \cos c \sin d$$
$$\sin(c-d) = \sin c \cos d - \cos c \sin d$$
**Spectrum of sinc(2000$\pi$t)**
![[Pasted image 20250919204449.png]]

![[Pasted image 20250919234925.png]]![[Pasted image 20250920010342.png]]
- FM Demodulation
![[Pasted image 20250920010718.png]]